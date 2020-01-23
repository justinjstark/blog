+++
title="This Is a Test Post"
description="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat."
draft="true"
tags=["Software", "Parenting"]
+++

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

This is .NET Framework implementation of Enumerable.Aggregate method with only one paramater func.

```csharp
public static TSource Aggregate<TSource>(
    this IEnumerable<TSource> source,
    Func<TSource, TSource, TSource> func)
{
    if (source == null) throw Error.ArgumentNull("source");
    if (func == null) throw Error.ArgumentNull("func");

    using (IEnumerator<TSource> e = source.GetEnumerator())
    {
        if (!e.MoveNext()) throw Error.NoElements();
        TSource result = e.Current;
        while (e.MoveNext()) {
            result = func(result, e.Current);
        }
        return result;
    }
}
```