---
title: Test Post
tags:
- Test1
- Test2
draft: true
---

This is a test post.

```js
function ProfilePage(props) {
  const showMessage = () => {
    alert('Followed ' + props.user);
  };

  const handleClick = () => {
    setTimeout(showMessage, 3000);
  };

  return (
    <button onClick={handleClick}>Follow</button>
  );
}
```

```csharp
public void Main(string[] args)
{
    var justin = "stark";
}
```

```csharp {hl_lines=[3]}
public Dictionary<string, List<string>> GetAllAttributes(string attributesXml)
{
    return _productAttributeParser.ParseProductAttributeMappings(attributesXml)
        .SelectMany(productAttributeMapping => productAttributeMapping.ShouldHaveValues()
            ? _productAttributeParser.ParseProductAttributeValues(attributesXml, productAttributeMapping.Id)
                .Select(pav => (productAttributeMapping.ProductAttribute.Name, pav.Name))
            : _productAttributeParser.ParseValues(attributesXml, productAttributeMapping.Id)
                .Select(value => (productAttributeMapping.ProductAttribute.Name, value)))
        .GroupBy(p => p.Item1)
        .ToDictionary(g => g.Key, g => g.Select(v => v.Item2).ToList());
}
```