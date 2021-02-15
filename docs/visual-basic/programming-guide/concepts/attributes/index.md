---
description: 'Más información sobre: información general sobre los atributos (Visual Basic)'
title: Información general de atributos
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: f25e69452f0af1c89af667619e673f8906704d1f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100437727"
---
# <a name="attributes-overview-visual-basic"></a>Información general sobre los atributos (Visual Basic)

Los atributos proporcionan un método eficaz para asociar metadatos, o información declarativa, con código (ensamblados, tipos, métodos, propiedades, etc.). Después de asociar un atributo con una entidad de programa, se puede consultar el atributo en tiempo de ejecución mediante la utilización de una técnica denominada *reflexión*. Para más información, vea [Reflexión (Visual Basic)](../reflection.md).

Los atributos tienen las propiedades siguientes:

- Los atributos agregan metadatos al programa. Los *metadatos* son información sobre los tipos definidos en un programa. Todos los ensamblados .NET contienen un conjunto de metadatos específico que describe los tipos y miembros de tipo definidos en el ensamblado. Puede agregar atributos personalizados para especificar cualquier información adicional que sea necesaria. Para más información, vea [Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic]).

- Puede aplicar uno o más atributos a todos los ensamblados, módulos o elementos de programa más pequeños como clases y propiedades.

- Los atributos pueden aceptar argumentos de la misma manera que los métodos y las propiedades.

- El programa puede examinar sus propios metadatos o los metadatos de otros programas mediante la reflexión. Para más información, vea [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic]).

## <a name="using-attributes"></a>Utilizar atributos

Los atributos se pueden colocar en la mayoría de las declaraciones, aunque un determinado atributo podría restringir los tipos de declaraciones en que es válido. En Visual Basic, un atributo está entre corchetes angulares ( \< > ). Debe aparecer inmediatamente antes del elemento al que se aplica, en la misma línea.

En este ejemplo, el atributo <xref:System.SerializableAttribute> se usa para aplicar una característica específica a una clase:

```vb
<System.Serializable()> Public Class SampleClass
    ' Objects of this type can be serialized.
End Class
```

 Un método con el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> se declara de esta forma:

```vb
Imports System.Runtime.InteropServices
```

```vb
<System.Runtime.InteropServices.DllImport("user32.dll")>
Sub SampleMethod()
End Sub
```

En una declaración se puede colocar más de un atributo:

```vb
Imports System.Runtime.InteropServices
```

```vb
Sub MethodA(<[In](), Out()> ByVal x As Double)
End Sub
Sub MethodB(<Out(), [In]()> ByVal x As Double)
End Sub
```

Algunos atributos se pueden especificar más de una vez para una entidad determinada. Un ejemplo de este tipo de atributos multiuso es <xref:System.Diagnostics.ConditionalAttribute>:

```vb
<Conditional("DEBUG"), Conditional("TEST1")>
Sub TraceMethod()
End Sub
```

> [!NOTE]
> Por convención, todos los nombres de atributos terminan con la palabra "Attribute" para distinguirlos de otros elementos de .NET Framework. Sin embargo, no es necesario especificar el sufijo de atributo cuando utiliza atributos en el código. Por ejemplo, `[DllImport]` es equivalente a `[DllImportAttribute]`, pero `DllImportAttribute` es el nombre del atributo real en .NET Framework.

### <a name="attribute-parameters"></a>Parámetros de atributo

Muchos atributos tienen parámetros, que pueden ser posicionales, sin nombre o con nombre. Los parámetros posicionales deben especificarse en un determinado orden y no se pueden omitir; los parámetros con nombre son opcionales y se pueden especificar en cualquier orden. Los parámetros posicionales se especifican en primer lugar. Por ejemplo, estos tres atributos son equivalentes:

```vb
<DllImport("user32.dll")>
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>
```

El primer parámetro, el nombre del archivo DLL, es posicional y siempre va primero; los demás tienen un nombre. En este caso, ambos parámetros con nombre tienen el estado false de forma predeterminada, por lo que se pueden omitir. Consulte la documentación del atributo individual para obtener información sobre los valores de parámetro predeterminados.

### <a name="attribute-targets"></a>Destinos de atributo

El *destino* de un atributo es la entidad a la que se aplica el atributo. Por ejemplo, puede aplicar un atributo a una clase, un método determinado o un ensamblado completo. De forma predeterminada, el atributo se aplica al elemento que lo precede. Pero puede identificar explícitamente, por ejemplo, si se aplica un atributo a un método, a su parámetro o a su valor devuelto.

Para identificar un destino de atributo de forma explícita, use la sintaxis siguiente:

```vb
<target : attribute-list>
```

La lista de posibles valores `target` se muestra en la tabla siguiente.

|Valor del objetivo|Se aplica a|
|------------------|----------------|
|`assembly`|Ensamblado completo|
|`module`|Módulo del ensamblado actual (que es diferente de un módulo de Visual Basic)|

 En el ejemplo siguiente se muestra cómo aplicar atributos a ensamblados y módulos. Para más información, vea [Atributos comunes (Visual Basic)](common-attributes.md).

```vb
Imports System.Reflection
<Assembly: AssemblyTitleAttribute("Production assembly 4"),
Module: CLSCompliant(True)>
```

## <a name="common-uses-for-attributes"></a>Usos comunes de los atributos

La lista siguiente incluye algunos de los usos comunes de atributos en el código:

- Marcar métodos con el atributo `WebMethod` en los servicios web para indicar que el método debe ser invocable a través del protocolo SOAP. Para obtener más información, vea <xref:System.Web.Services.WebMethodAttribute>.

- Describir cómo serializar parámetros de método al interoperar con código nativo. Para obtener más información, vea <xref:System.Runtime.InteropServices.MarshalAsAttribute>.

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

- [Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])

- [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])

- [How to: Create a C/C++ Union by Using Attributes (Visual Basic)](how-to-create-a-c-cpp-union-by-using-attributes.md) (Creación de uniones de C/C++ mediante la utilización de atributos [Visual Basic])

- [Common Attributes (Visual Basic)](common-attributes.md) (Atributos comunes [Visual Basic])

- [Información del llamador (Visual Basic)](../caller-information.md)

## <a name="see-also"></a>Consulte también

- [Guía de programación en Visual Basic](../../index.md)
- [Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])
- [Atributos](../../../../standard/attributes/index.md)
