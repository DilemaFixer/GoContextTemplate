
## Value Types

```go
const (
    TypeString
    TypeInt
    TypeUint
    TypeFloat
    TypeBool
    TypeObject
)
```

## Initialization

```go
func NewContext(obj *any) *Context
```

## Layer Management

```go
func (c *Context) SetCurrentLayer(layer int)
func (c *Context) GetCurrentLayer() int
```

## Setting Values

### Regular methods
```go
func (c *Context) Set(key string, value any)
func (c *Context) SetString(key, value string)
func (c *Context) SetInt(key string, value int64)
func (c *Context) SetUint(key string, value uint64)
func (c *Context) SetFloat(key string, value float64)
func (c *Context) SetBool(key string, value bool)
func (c *Context) SetObject(key string, value any)
```

### Layered methods
```go
func (c *Context) SetLayered(key string, value any)
func (c *Context) SetStringLayered(key, value string)
func (c *Context) SetIntLayered(key string, value int64)
func (c *Context) SetUintLayered(key string, value uint64)
func (c *Context) SetFloatLayered(key string, value float64)
func (c *Context) SetBoolLayered(key string, value bool)
func (c *Context) SetObjectLayered(key string, value any)
```

## Getting Values

### Regular methods
```go
func (c *Context) String(key string) string
func (c *Context) Int(key string) int64
func (c *Context) Uint(key string) uint64
func (c *Context) Float(key string) float64
func (c *Context) Bool(key string) bool
func (c *Context) Object(key string) any
```

### Layered methods
```go
func (c *Context) StringLayered(key string) string
func (c *Context) IntLayered(key string) int64
func (c *Context) UintLayered(key string) uint64
func (c *Context) FloatLayered(key string) float64
func (c *Context) BoolLayered(key string) bool
func (c *Context) ObjectLayered(key string) any
```

### Safe retrieval with existence check

```go
func (c *Context) Get(key string) (any, ValueType, bool)
func (c *Context) GetLayered(key string) (any, ValueType, bool)
func (c *Context) GetString(key string) (string, bool)
func (c *Context) GetStringLayered(key string) (string, bool)
// ... similar for all types
```

## Existence Check

```go
func (c *Context) HasString(key string) bool
func (c *Context) HasStringLayered(key string) bool
// ... similar for all types
```

## Type Detection

```go
func (c *Context) Type(key string) ValueType
```

## Deleting Values

```go
func (c *Context) Delete(key string)
func (c *Context) DeleteLayered(key string)
func (c *Context) DeleteString(key string)
func (c *Context) DeleteStringLayered(key string)
// ... similar for all types
```

## Getting Keys

```go
func (c *Context) StringKeys() []string
func (c *Context) IntKeys() []string
// ... for all types
func (c *Context) AllKeys() []string
```

## Copying and Merging

```go
func (c *Context) CopyStrings() map[string]string
func (c *Context) CopyInts() map[string]int64
// ... for all types

func (c *Context) MergeStrings(other map[string]string)
func (c *Context) MergeInts(other map[string]int64)
// ... for all types
```

## Utilities

```go
func (c *Context) GetValueOfThisLayer(key string) any
```
