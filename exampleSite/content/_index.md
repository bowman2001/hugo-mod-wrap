---
title: Hugo module for wrapping Markdown safely in a div tag
---

The module provides the two shortcodes `begin` and `end` which have always to be used in pairs. Each pair expects the same string as its parameter. It contains a class or list of classes that is injected into the resulting div wrapper. These pairs can be nested.

The module also includes a partial `hugo-mod-wrap/check` that needs to be included after the content at the bottom of the `body` tag. It watches out for `begin` shortcodes without a closing `end`.

## Example

{{< begin "grey" >}}
### Grey
{{< begin "red" >}}
#### Red
{{% pangram 5 %}}
{{< end "red" >}}

{{< begin "green" >}}
#### Green
{{% pangram 5 %}}
{{< end "green" >}}

{{< begin "blue" >}}
#### Blue
{{% pangram 5 %}}
{{< end "blue" >}}

{{< begin "half red" >}}
{{% pangram 3 %}}
{{< end "half red" >}}
{{< begin "half green" >}}
{{% pangram 3 %}}
{{< end "half green" >}}
{{< end "grey" >}}
