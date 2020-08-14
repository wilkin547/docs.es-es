---
ms.openlocfilehash: 54ef49755dc0b9d1b821ae7999ab218626d455e1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556347"
---
### <a name="custom-encoderfallbackbuffer-instances-cannot-fall-back-recursively"></a>No se puede recurrir de formar recursiva a las instancias personalizadas de EncoderFallbackBuffer

No se puede recurrir de formar recursiva a las instancias personalizadas de <xref:System.Text.EncoderFallbackBuffer>. La implementación de <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> debe traducirse en una secuencia de caracteres que se pueda convertir a la codificación de destino. De lo contrario, se produce una excepción.

#### <a name="change-description"></a>Descripción del cambio

Durante una operación de transcodificación de caracteres a bytes, el runtime detecta secuencias UTF-16 de formato incorrecto o no convertibles y proporciona esos caracteres al método <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>. El método `Fallback` determina los caracteres que han de sustituirse por los datos originales no convertibles y estos caracteres se drenan llamando a <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> en un bucle.

El runtime intenta luego transcodificar estos caracteres de sustitución en la codificación de destino. Si esta operación se realiza correctamente, el runtime continúa con la transcodificación desde donde se quedó en la cadena de entrada original.

Antes, las implementaciones personalizadas de <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> pueden devolver secuencias de caracteres que no se pueden convertir en la codificación de destino. Si los caracteres sustituidos no se pueden transcodificar en la codificación de destino, el runtime vuelve a invocar el método <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> con los caracteres de sustitución, esperando que el método <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> devuelva una nueva secuencia de sustitución. Este proceso continúa hasta que el runtime ve finalmente una sustitución convertible de formato correcto o hasta que se alcanza un número máximo de repeticiones.

A partir de .NET Core 3.0, las implementaciones personalizadas de <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType> deben devolver secuencias de caracteres que se pueden convertir en la codificación de destino. Si los caracteres sustituidos no se pueden transcodificar en la codificación de destino, se produce una <xref:System.ArgumentException>. El runtime ya no realizará llamadas recursivas a la instancia de <xref:System.Text.EncoderFallbackBuffer>.

Este comportamiento solo se aplica cuando se cumplen las tres condiciones siguientes:

- El runtime detecta una secuencia UTF-16 de formato incorrecto o una secuencia UTF-16 que no se puede convertir en la codificación de destino.
- Se ha especificado un <xref:System.Text.EncoderFallback> personalizado.
- El <xref:System.Text.EncoderFallback> personalizado intenta sustituir una nueva secuencia UTF-16 con formato incorrecto o no convertible.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

La mayoría de los desarrolladores no tienen que realizar ninguna acción.

Si una aplicación usa un objeto <xref:System.Text.EncoderFallback> personalizado con una clase <xref:System.Text.EncoderFallbackBuffer>, asegúrese de que la implementación de <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> rellena el búfer de reserva con datos UTF-16 de formato correcto que se puedan convertir directamente en la codificación de destino cuando el runtime invoque por primera vez el método <xref:System.Text.EncoderFallbackBuffer.Fallback%2A>.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType>
- <xref:System.Text.EncoderFallbackBuffer.GetNextChar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.EncoderFallbackBuffer.Fallback`
- `M:System.Text.EncoderFallbackBuffer.GetNextChar`

-->
