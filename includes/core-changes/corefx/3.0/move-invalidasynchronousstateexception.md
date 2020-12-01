---
ms.openlocfilehash: 78678b4b352bb063d1521e9aee3492c0cee059b8
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032136"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>Se ha movido InvalidAsynchronousStateException a otro ensamblado

La clase <xref:System.ComponentModel.InvalidAsynchronousStateException> se ha movido.

#### <a name="change-description"></a>Descripción del cambio

En .NET Core 2.2 y en versiones anteriores, la clase <xref:System.ComponentModel.InvalidAsynchronousStateException> se encuentra en el ensamblado *System.ComponentModel.TypeConverter*.

A partir de .NET Core 3.0, se encuentra en el ensamblado *System.ComponentModel.Primitives*.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Este cambio solo afecta a las aplicaciones que usan la reflexión para cargar <xref:System.ComponentModel.InvalidAsynchronousStateException> mediante la llamada a un método como <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, o una sobrecarga de <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> que supone que el tipo está en un ensamblado determinado. En ese caso, actualice el ensamblado al que se hace referencia en la llamada de método para reflejar la nueva ubicación del ensamblado del tipo.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

Ninguno.

<!--

#### Affected APIs

- Not detectable via API analysis

-->
