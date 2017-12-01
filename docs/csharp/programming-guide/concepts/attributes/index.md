---
title: Atributos (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f148f13f-a0d5-4f22-9c87-4b73d5dde270
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2993ef3f424aa6487681e194f21e0f82193342ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="attributes-c"></a>Atributos (C#)
Los atributos proporcionan un método eficaz para asociar metadatos, o información declarativa, con código (ensamblados, tipos, métodos, propiedades, etc.). Después de asociar un atributo con una entidad de programa, se puede consultar el atributo en tiempo de ejecución mediante la utilización de una técnica denominada *reflexión*. Para obtener más información, vea [Reflexión (C#)](../../../../csharp/programming-guide/concepts/reflection.md).  
  
 Los atributos tienen las propiedades siguientes:  
  
-   Los atributos agregan metadatos al programa. Los *metadatos* son información sobre los tipos definidos en un programa. Todos los ensamblados .NET contienen un conjunto de metadatos específico que describe los tipos y miembros de tipo definidos en el ensamblado. Puede agregar atributos personalizados para especificar cualquier información adicional que sea necesaria. Para obtener más información, vea [Crear atributos personalizados (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).  
  
-   Puede aplicar uno o más atributos a todos los ensamblados, módulos o elementos de programa más pequeños como clases y propiedades.  
  
-   Los atributos pueden aceptar argumentos de la misma manera que los métodos y las propiedades.  
  
-   El programa puede examinar sus propios metadatos o los metadatos de otros programas mediante la reflexión. Para obtener más información, consulte [Acceder a atributos mediante reflexión (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).  
  
## <a name="using-attributes"></a>Utilizar atributos  
 Los atributos se pueden colocar en la mayoría de las declaraciones, aunque un determinado atributo podría restringir los tipos de declaraciones en que es válido. En C#, se especifica un atributo al colocar el nombre del atributo, encerrado entre corchetes ([]), encima de la declaración de la entidad a la que se aplica.  
  
 En este ejemplo, el atributo <xref:System.SerializableAttribute> se usa para aplicar una característica específica a una clase:  
  
```csharp  
[System.Serializable]  
public class SampleClass  
{  
    // Objects of this type can be serialized.  
}  
```  
  
 Un método con el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> se declara de esta forma:  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
[System.Runtime.InteropServices.DllImport("user32.dll")]  
extern static void SampleMethod();  
```  
  
 En una declaración se puede colocar más de un atributo:  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
void MethodA([In][Out] ref double x) { }  
void MethodB([Out][In] ref double x) { }  
void MethodC([In, Out] ref double x) { }  
```  
  
 Algunos atributos se pueden especificar más de una vez para una entidad determinada. Un ejemplo de este tipo de atributos multiuso es <xref:System.Diagnostics.ConditionalAttribute>:  
  
```csharp  
[Conditional("DEBUG"), Conditional("TEST1")]  
void TraceMethod()  
{  
    // ...  
}  
```  
  
> [!NOTE]
>  Por convención, todos los nombres de atributos terminan con la palabra "Attribute" para distinguirlos de otros elementos de .NET Framework. Sin embargo, no es necesario especificar el sufijo de atributo cuando utiliza atributos en el código. Por ejemplo, `[DllImport]` es equivalente a `[DllImportAttribute]`, pero `DllImportAttribute` es el nombre del atributo real en .NET Framework.  
  
### <a name="attribute-parameters"></a>Parámetros de atributo  
 Muchos atributos tienen parámetros, que pueden ser posicionales, sin nombre o con nombre. Los parámetros posicionales deben especificarse en un determinado orden y no se pueden omitir; los parámetros con nombre son opcionales y se pueden especificar en cualquier orden. Los parámetros posicionales se especifican en primer lugar. Por ejemplo, estos tres atributos son equivalentes:  
  
```csharp  
[DllImport("user32.dll")]  
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]  
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]  
```  
  
 El primer parámetro, el nombre del archivo DLL, es posicional y siempre va primero; los demás tienen un nombre. En este caso, ambos parámetros con nombre tienen el estado false de forma predeterminada, por lo que se pueden omitir. Consulte la documentación del atributo individual para obtener información sobre los valores de parámetro predeterminados.  
  
### <a name="attribute-targets"></a>Destinos de atributo  
 El *destino* de un atributo es la entidad a la que se aplica el atributo. Por ejemplo, puede aplicar un atributo a una clase, un método determinado o un ensamblado completo. De forma predeterminada, el atributo se aplica al elemento que lo precede. Pero puede identificar explícitamente, por ejemplo, si se aplica un atributo a un método, a su parámetro o a su valor devuelto.  
  
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
|`event`|Evento|  
|`method`|Método o descriptores de acceso de propiedad `get` y `set`|  
|`param`|Parámetros de método o parámetros de descriptor de acceso de propiedad `set`|  
|`property`|Propiedad|  
|`return`|Valor devuelto de un método, indexador de propiedad o descriptor de acceso de propiedad `get`|  
|`type`|Estructura, clase, interfaz, enumeración o delegado|  
  
 En el ejemplo siguiente se muestra cómo aplicar atributos a ensamblados y módulos. Para obtener más información, vea [Atributos comunes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).  
  
```csharp  
using System;  
using System.Reflection;  
[assembly: AssemblyTitleAttribute("Production assembly 4")]  
[module: CLSCompliant(true)]  
```  
  
 En el ejemplo siguiente, se muestra cómo aplicar atributos a métodos, parámetros de método y valores devueltos por métodos en C#.  
  
```csharp  
// default: applies to method  
[SomeAttr]  
int Method1() { return 0; }  
  
// applies to method  
[method: SomeAttr]  
int Method2() { return 0; }  
  
// applies to return value  
[return: SomeAttr]  
int Method3() { return 0; }  
```  
  
> [!NOTE]
>  Independientemente de los destinos en los que `SomeAttr` se define para que sea válido, debe especificarse el destino `return`, incluso si `SomeAttr` se ha definido para que se aplique solo a los valores devueltos. En otras palabras, el compilador no usará información de `AttributeUsage` para resolver destinos de atributo ambiguos. Para obtener más información, consulte [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).  
  
## <a name="common-uses-for-attributes"></a>Usos comunes de los atributos  
 La lista siguiente incluye algunos de los usos comunes de atributos en el código:  
  
-   Marcar métodos con el atributo `WebMethod` en los servicios web para indicar que el método debe ser invocable a través del protocolo SOAP. Para obtener más información, consulta <xref:System.Web.Services.WebMethodAttribute>.  
  
-   Describir cómo serializar parámetros de método al interoperar con código nativo. Para obtener más información, consulta <xref:System.Runtime.InteropServices.MarshalAsAttribute>.  
  
-   Describir las propiedades COM para clases, métodos e interfaces.  
  
-   Llamar al código no administrado mediante la clase <xref:System.Runtime.InteropServices.DllImportAttribute>.  
  
-   Describir los ensamblados en cuanto a título, versión, descripción o marca.  
  
-   Describir qué miembros de una clase serializar para la persistencia.  
  
-   Describir cómo realizar asignaciones entre los miembros de clase y los nodos XML para la serialización XML.  
  
-   Describir los requisitos de seguridad para los métodos.  
  
-   Especificar las características utilizadas para reforzar la seguridad.  
  
-   Controlar optimizaciones mediante el compilador Just-In-Time (JIT) para que el código siga siendo fácil de depurar.  
  
-   Obtener información sobre el llamador de un método.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información, consulte:  
  
-   [Crear atributos personalizados (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   [Acceder a atributos mediante reflexión (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
-   [Cómo: Crear una unión de C/C++ mediante atributos (C#)](../../../../csharp/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [Atributos comunes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
  
-   [Información del llamador (C#)](../../../../csharp/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)  
 [Reflexión (C#)](../../../../csharp/programming-guide/concepts/reflection.md)  
 [Atributos](https://msdn.microsoft.com/library/5x6cd29c)
