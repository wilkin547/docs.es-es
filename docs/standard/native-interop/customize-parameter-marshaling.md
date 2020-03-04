---
title: 'Personalización de la serialización de parámetros: .NET'
description: Obtenga información sobre cómo personalizar la forma en que .NET serializa los parámetros de una representación nativa.
ms.date: 01/18/2019
ms.openlocfilehash: ff646ad942cf051ce90cd75b24c8562e536182d9
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159616"
---
# <a name="customizing-parameter-marshaling"></a>Personalización de la serialización de parámetros

Cuando el comportamiento predeterminado de serialización de los parámetros del entorno de ejecución de .NET no hace lo que desea, puede usar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> para personalizar cómo se serializan los parámetros.

## <a name="customizing-string-parameters"></a>Parámetros de cadenas de conexión

.NET tiene una serie de formatos de serialización de cadenas. Estos métodos se dividen en secciones distintas en cadenas de estilo C y formatos de cadena centrados en Windows.

### <a name="c-style-strings"></a>Cadenas de estilo C

Cada uno de estos formatos pasa una cadena terminada en valor NULL al código nativo. Se diferencian en la codificación de la cadena nativa.

| Valor de `System.Runtime.InteropServices.UnmanagedType` | Codificación |
|------------------------------------------------------|----------|
| LPStr | ANSI |
| LPUTF8Str | UTF-8 |
| LPWStr | UTF-16 |
| LPTStr | UTF-16 |

El formato <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> es un poco diferente. Al igual que `LPWStr`, serializa la cadena a una cadena de estilo C nativa codificada en UTF-16. Sin embargo, la firma administrada que tiene que pasar en la cadena por referencia y la firma nativa coincidente toma la cadena por valor. Esta distinción permite usar una API nativa que toma una cadena por valor y la modifica en contexto sin tener que usar `StringBuilder`. Se recomienda no usar manualmente este formato, ya que es propenso a provocar confusión con las firmas no coincidentes nativas y administradas.

### <a name="windows-centric-string-formats"></a>Formatos de cadena centrados en Windows

Al interactuar con interfaces COM u OLE, probablemente descubrirá que las funciones nativas toman cadenas como argumentos `BSTR`. Puede usar el tipo <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> no administrado para serializar una cadena como `BSTR`.

Si está interactuando con API de WinRT, puede usar el formato <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> para serializar una cadena como `HSTRING`.

## <a name="customizing-array-parameters"></a>Personalización de parámetros de matriz

.NET también proporciona varias maneras de serializar los parámetros de matriz. Si está llamando a una API que toma una matriz de estilo C, use el tipo <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType> no administrado. Si los valores de la matriz necesitan una serialización personalizada, puede usar el campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> en el atributo `[MarshalAs]` de dicho campo.

Si usa API de COM, probablemente tendrá que serializar los parámetros de matriz como `SAFEARRAY*`. Para ello, puede usar el tipo <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> no administrado. El tipo predeterminado de los elementos de `SAFEARRAY` puede verse en la tabla sobre cómo [personalizar campos `object`](./customize-struct-marshaling.md#marshaling-systemobjects). Puede usar campos <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> y <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> para personalizar el tipo de elemento exacto de `SAFEARRAY`.

## <a name="customizing-boolean-or-decimal-parameters"></a>Personalización de los parámetros booleanos o decimales

Para obtener información sobre la serialización de parámetros booleanos o decimales, consulte [Personalización de la serialización de estructuras](customize-struct-marshaling.md).

## <a name="customizing-object-parameters-windows-only"></a>Personalización de parámetros de objeto (solo Windows)

En Windows, el entorno de ejecución de .NET proporciona diferentes formas de serializar parámetros de objetos al código nativo.

### <a name="marshaling-as-specific-com-interfaces"></a>Serialización como interfaces COM específicas

Si la API toma un puntero a un objeto COM, puede usar cualquiera de los siguientes formatos `UnmanagedType` en un parámetro con el tipo `object` para indicar a .NET que serialice estas interfaces específicas:

- `IUnknown`
- `IDispatch`
- `IInspectable`

Además, si el tipo se marca como `[ComVisible(true)]` o si está serializando el tipo `object`, puede usar el formato <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> para serializar el objeto como un contenedor CCW para la vista COM del tipo.

### <a name="marshaling-to-a-variant"></a>Calcular las referencias a un `VARIANT`

Si la API nativa toma un tipo `VARIANT` de Win32, puede usar el formato <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> en su parámetro `object` para serializar los objetos como `VARIANT`. Consulte la documentación sobre cómo [personalizar campos `object`](customize-struct-marshaling.md#marshaling-systemobjects) para realizar una asignación entre tipos .NET y `VARIANT`.

### <a name="custom-marshalers"></a>Serializadores personalizados

Si desea proyectar una interfaz COM nativa en un tipo administrado diferente, puede usar el formato `UnmanagedType.CustomMarshaler` y una implementación de <xref:System.Runtime.InteropServices.ICustomMarshaler> para proporcionar su propio código de serialización personalizado.
