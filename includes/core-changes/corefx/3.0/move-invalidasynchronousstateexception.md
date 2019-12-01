---
ms.openlocfilehash: 82835915efa0e113e81bb09bd5062ee3252f2a64
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568228"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>Se ha movido InvalidAsynchronousStateException a otro ensamblado

La clase <xref:System.ComponentModel.InvalidAsynchronousStateException> se ha movido.

#### <a name="change-description"></a>Descripción del cambio

En .NET Core 2.2 y en versiones anteriores, la clase <xref:System.ComponentModel.InvalidAsynchronousStateException> se encuentra en el ensamblado *System.ComponentModel.TypeConverter*.

A partir de .NET Core 3.0, se encuentra en el ensamblado *System.ComponentModel.Primitives*.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Este cambio solo afecta a las aplicaciones que usan la reflexión para cargar <xref:System.ComponentModel.InvalidAsynchronousStateException> mediante la llamada a un método como <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, o una sobrecarga de <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> que supone que el tipo está en un ensamblado determinado. En ese caso, el ensamblado al que se hace referencia en la llamada al método debe actualizarse para reflejar la nueva ubicación del ensamblado del tipo.

#### <a name="category"></a>Categoría

CoreFX

#### <a name="affected-apis"></a>API afectadas

- None

<!--

### Affected APIs

- Not detectable via API analysis

-->
