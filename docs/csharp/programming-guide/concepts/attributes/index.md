---
title: Atributos (C#)
ms.date: 04/26/2018
ms.openlocfilehash: 2a07035ea97bb0ff1a8f4793fe8a30d3a42c34a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79397645"
---
# <a name="attributes-c"></a>Atributos (C#)

Los atributos proporcionan un método eficaz para asociar metadatos, o información declarativa, con código (ensamblados, tipos, métodos, propiedades, etc.). Después de asociar un atributo con una entidad de programa, se puede consultar el atributo en tiempo de ejecución mediante la utilización de una técnica denominada *reflexión*. Para obtener más información, vea [Reflexión (C#)](../reflection.md).

Los atributos tienen las propiedades siguientes:

- Los atributos agregan metadatos al programa. Los *metadatos* son información sobre los tipos definidos en un programa. Todos los ensamblados .NET contienen un conjunto de metadatos específico que describe los tipos y miembros de tipo definidos en el ensamblado. Puede agregar atributos personalizados para especificar cualquier información adicional que sea necesaria. Para obtener más información, vea [Crear atributos personalizados (C#)](creating-custom-attributes.md).
- Puede aplicar uno o más atributos a todos los ensamblados, módulos o elementos de programa más pequeños como clases y propiedades.
- Los atributos pueden aceptar argumentos de la misma manera que los métodos y las propiedades.
- El programa puede examinar sus propios metadatos o los metadatos de otros programas mediante la reflexión. Para obtener más información, consulte [Acceder a atributos mediante reflexión (C#)](accessing-attributes-by-using-reflection.md).

## <a name="using-attributes"></a>Uso de atributos

Los atributos se pueden colocar en la mayoría de las declaraciones, aunque un determinado atributo podría restringir los tipos de declaraciones en que es válido. En C#, para especificar un atributo se coloca su nombre entre corchetes ([]) por encima de la declaración de la entidad a la que se aplica.

En este ejemplo, el atributo <xref:System.SerializableAttribute> se usa para aplicar una característica específica a una clase:

[!code-csharp[Using the serializable attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#1)]

Un método con el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> se declara como en el siguiente ejemplo:

[!code-csharp[Declaring a method to import from an external library](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#2)]

En una declaración se puede colocar más de un atributo, como se muestra en el siguiente ejemplo:

[!code-csharp[Including the interop namespace](~/samples/snippets/csharp/attributes/AttributesOverview.cs#3)]
[!code-csharp[Declaring two way marshaling for arguments](~/samples/snippets/csharp/attributes/AttributesOverview.cs#4)]

Algunos atributos se pueden especificar más de una vez para una entidad determinada. Un ejemplo de este tipo de atributos multiuso es <xref:System.Diagnostics.ConditionalAttribute>:

[!code-csharp[Using the conditional attribute](~/samples/snippets/csharp/attributes/AttributesOverview.cs#5)]

> [!NOTE]
> Por convención, todos los nombres de atributos terminan con la palabra "Attribute" para distinguirlos de otros elementos de las bibliotecas de .NET. Sin embargo, no es necesario especificar el sufijo de atributo cuando utiliza atributos en el código. Por ejemplo, `[DllImport]` es equivalente a `[DllImportAttribute]`, pero `DllImportAttribute` es el nombre real del atributo en la biblioteca de clases .NET Framework.

### <a name="attribute-parameters"></a>Parámetros de atributo

Muchos atributos tienen parámetros, que pueden ser posicionales, sin nombre o con nombre. Los parámetros posicionales deben especificarse en un orden determinado y no se pueden omitir. Los parámetros con nombre son opcionales y pueden especificarse en cualquier orden. Los parámetros posicionales se especifican en primer lugar. Por ejemplo, estos tres atributos son equivalentes:

```csharp
[DllImport("user32.dll")]
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]
```

El primer parámetro, el nombre del archivo DLL, es posicional y siempre va primero; los demás tienen un nombre. En este caso, ambos parámetros con nombre tienen el estado false de forma predeterminada, por lo que se pueden omitir. Los parámetros posicionales corresponden a los parámetros del constructor de atributos. Los parámetros con nombre u opcionales corresponden a propiedades o campos del atributo. Consulte la documentación del atributo individual para obtener información sobre los valores de parámetro predeterminados.

### <a name="attribute-targets"></a>Destinos de atributo

El *destino* de un atributo es la entidad a la que se aplica dicho atributo. Por ejemplo, puede aplicar un atributo a una clase, un método determinado o un ensamblado completo. De forma predeterminada, el atributo se aplica al elemento que sigue. Pero puede identificar explícitamente, por ejemplo, si se aplica un atributo a un método, a su parámetro o a su valor devuelto.

Para identificar un destino de atributo de forma explícita, use la sintaxis siguiente:

```csharp
[target : attribute-list]
```

La lista de posibles valores `target` se muestra en la tabla siguiente.

|Valor del objetivo|Se aplica a|
|------------------|----------------|
|`assembly`|Ensamblado completo|
|`module`|Módulo de ensamblado actual|
|`field`|Campo de una clase o un struct|
|`event`|evento|
|`method`|Método o descriptores de acceso de propiedad `get` y `set`|
|`param`|Parámetros de método o parámetros de descriptor de acceso de propiedad `set`|
|`property`|Property|
|`return`|Valor devuelto de un método, indexador de propiedad o descriptor de acceso de propiedad `get`|
|`type`|Estructura, clase, interfaz, enumeración o delegado|

Debe especificar el valor de destino `field` para aplicar un atributo al campo de respaldo creado para una [propiedad implementada automáticamente](../../../properties.md).

En el ejemplo siguiente se muestra cómo aplicar atributos a ensamblados y módulos. Para obtener más información, vea [Atributos comunes (C#)](common-attributes.md).

```csharp
using System;
using System.Reflection;
[assembly: AssemblyTitleAttribute("Production assembly 4")]
[module: CLSCompliant(true)]
```

En el ejemplo siguiente, se muestra cómo aplicar atributos a métodos, parámetros de método y valores devueltos por métodos en C#.

[!code-csharp[Applying attributes to different code elements](../../../../../samples/snippets/csharp/attributes/AttributesOverview.cs#6)]

> [!NOTE]
> Independientemente de los destinos en los que `ValidatedContract` se define para que sea válido, debe especificarse el destino `return`, incluso si `ValidatedContract` se ha definido para que se aplique solo a los valores devueltos. En otras palabras, el compilador no usará información de `AttributeUsage` para resolver destinos de atributo ambiguos. Para obtener más información, consulte [AttributeUsage (C#)](attributeusage.md).

## <a name="common-uses-for-attributes"></a>Usos comunes de los atributos

La lista siguiente incluye algunos de los usos comunes de atributos en el código:

- Marcar métodos con el atributo `WebMethod` en los servicios web para indicar que el método debe ser invocable a través del protocolo SOAP. Para obtener más información, consulta <xref:System.Web.Services.WebMethodAttribute>.
- Describir cómo serializar parámetros de método al interoperar con código nativo. Para obtener más información, consulta <xref:System.Runtime.InteropServices.MarshalAsAttribute>.
- Describir las propiedades COM para clases, métodos e interfaces.
- Llamar al código no administrado mediante la clase <xref:System.Runtime.InteropServices.DllImportAttribute>.
- Describir los ensamblados en cuanto a título, versión, descripción o marca.
- Describir qué miembros de una clase serializar para la persistencia.
- Describir cómo realizar asignaciones entre los miembros de clase y los nodos XML para la serialización XML.
- Describir los requisitos de seguridad para los métodos.
- Especificar las características utilizadas para reforzar la seguridad.
- Controlar optimizaciones mediante el compilador Just-In-Time (JIT) para que el código siga siendo fácil de depurar.
- Obtener información sobre el llamador de un método.

## <a name="related-sections"></a>Secciones relacionadas

Para obtener más información, consulte:

- [Crear atributos personalizados (C#)](creating-custom-attributes.md)  
- [Acceder a atributos mediante reflexión (C#)](accessing-attributes-by-using-reflection.md)  
- [Procedimiento para: Crear una unión de C/C++ mediante atributos (C#)](how-to-create-a-c-cpp-union-by-using-attributes.md)  
- [Atributos comunes (C#)](common-attributes.md)  
- [Información del llamador (C#)](../caller-information.md)  

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../index.md)
- [Reflexión (C#)](../reflection.md)
- [Atributos](../../../../standard/attributes/index.md)
- [Uso de atributos en C#](../../../tutorials/attributes.md)
