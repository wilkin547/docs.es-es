---
title: Atributos comunes (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f470e6ff3e316076d71a34346f741cc4504471a3
ms.lasthandoff: 03/13/2017

---
# <a name="common-attributes-visual-basic"></a>Atributos comunes (Visual Basic)
En este tema se describe los atributos que se utilizan normalmente en programas de Visual Basic.  
  
-   [Atributos globales](#Global)  
  
-   [Obsolete (atributo)](#Obsolete)  
  
-   [Atributo condicional](#Conditional)  
  
-   [Atributos de información del llamador](#CallerInfo)  
  
-   [Atributos de Visual Basic](#VB)  
  
##  <a name="Global"></a>Atributos globales  
 Mayoría de los atributos se aplica a elementos específicos del lenguaje, como clases o métodos; Sin embargo, algunos atributos son globales, se aplican a todo un ensamblado o módulo. Por ejemplo, el <xref:System.Reflection.AssemblyVersionAttribute>atributo puede utilizarse para incrustar información de versión en un ensamblado, como esta:</xref:System.Reflection.AssemblyVersionAttribute>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 Los atributos globales aparecen en el código fuente después de cualquier nivel superior`Imports` instrucciones y antes de las declaraciones de espacio de nombres, módulo o tipo. Los atributos globales pueden aparecer en varios archivos de origen, pero los archivos se deben compilar en un paso de compilación único. Para los proyectos de Visual Basic, los atributos globales se colocan generalmente en el archivo AssemblyInfo.vb (el archivo se crea automáticamente cuando se crea un proyecto en Visual Studio).  
  
 Los atributos de ensamblado son valores que proporcionan información sobre un ensamblado. Se dividen en las siguientes categorías:  
  
-   Atributos de identidad de ensamblado  
  
-   Atributos de información  
  
-   Atributos de manifiesto del ensamblado  
  
### <a name="assembly-identity-attributes"></a>Atributos de identidad del ensamblado  
 Tres atributos (con un nombre seguro, si es aplicable) determinan la identidad de un ensamblado: nombre, versión y referencia cultural. Estos atributos forman el nombre completo del ensamblado y son necesarios cuando se hace referencia en el código. Puede establecer la versión y la referencia cultural utilizando los atributos de un ensamblado. Sin embargo, se establece el valor de nombre por el compilador, el IDE de Visual Studio en el [cuadro de diálogo de información de ensamblado](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), o la herramienta Assembly Linker (Al.exe) cuando se crea el ensamblado, basándose en el archivo que contiene el manifiesto del ensamblado. El <xref:System.Reflection.AssemblyFlagsAttribute>atributo especifica si pueden coexistir varias copias del ensamblado.</xref:System.Reflection.AssemblyFlagsAttribute>  
  
 La siguiente tabla muestra los atributos de identidad.  
  
|Atributo|Propósito|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName>|Describe completamente la identidad de un ensamblado.|  
|<xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute>|Especifica la versión de un ensamblado.|  
|<xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute>|Especifica la cultura que admite el ensamblado.|  
|<xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute>|Especifica si un ensamblado admite la ejecución en paralelo en el mismo equipo, en el mismo proceso o en el mismo dominio de aplicación.|  
  
### <a name="informational-attributes"></a>Atributos informativos  
 Puede utilizar atributos informativos para proporcionar información adicional de la compañía o de producto para un ensamblado. La siguiente tabla muestra los atributos de información definidos en el <xref:System.Reflection?displayProperty=fullName>espacio de nombres.</xref:System.Reflection?displayProperty=fullName>  
  
|Atributo|Propósito|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute>|Define un atributo personalizado que especifica un nombre de producto para un manifiesto de ensamblado.|  
|<xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute>|Define un atributo personalizado que especifica una marca comercial para un manifiesto de ensamblado.|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute>|Define un atributo personalizado que especifica una versión informativa para un manifiesto de ensamblado.|  
|<xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute>|Define un atributo personalizado que especifica un nombre de compañía para un manifiesto de ensamblado.|  
|<xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute>|Define un atributo personalizado que especifica un copyright para un manifiesto de ensamblado.|  
|<xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute>|Indica al compilador que use un número de versión específico para el recurso de versión de archivo Win32.|  
|<xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute>|Indica si el ensamblado es compatible con Common Language Specification (CLS).|  
  
### <a name="assembly-manifest-attributes"></a>Atributos de manifiesto del ensamblado  
 Puede utilizar atributos de manifiesto del ensamblado para proporcionar información en el manifiesto del ensamblado. Esto incluye el título, descripción, alias predeterminado y configuración. La siguiente tabla muestra los atributos del manifiesto de ensamblado definen en el <xref:System.Reflection?displayProperty=fullName>espacio de nombres.</xref:System.Reflection?displayProperty=fullName>  
  
|Atributo|Propósito|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute>|Define un atributo personalizado que especifica un título de ensamblado para un manifiesto de ensamblado.|  
|<xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute>|Define un atributo personalizado que especifica una descripción de ensamblado para un manifiesto de ensamblado.|  
|<xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute>|Define un atributo personalizado que especifica una configuración de ensamblado (como versión comercial o de depuración) para un manifiesto de ensamblado.|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute>|Define un alias predeterminado descriptivo para un manifiesto de ensamblado|  
  
##  <a name="Obsolete"></a>Obsolete (atributo)  
 El `Obsolete` atributo marca una entidad del programa como uno que ya no se recomienda para su uso. Cada uso de una entidad marcada obsoleta generará posteriormente una advertencia o un error, según cómo esté configurado el atributo. Por ejemplo:  
  
```vb  
<System.Obsolete("use class B")>   
Class A  
    Sub Method()  
    End Sub  
End Class  
  
Class B  
    <System.Obsolete("use NewMethod", True)>   
    Sub OldMethod()  
    End Sub  
  
    Sub NewMethod()  
    End Sub  
End Class  
```  
  
 En este ejemplo el `Obsolete` atributo se aplica a la clase `A` y al método `B.OldMethod`. Dado que el segundo argumento del constructor del atributo aplicado a `B.OldMethod` está establecido en `true`, este método producirá un error del compilador, mientras que el uso de la clase `A` le solo generan una advertencia. Llamar a `B.NewMethod`, sin embargo, se genera ninguna advertencia o error.  
  
 La cadena proporcionada como primer argumento al constructor de atributos se mostrará como parte de la advertencia o error. Por ejemplo, cuando se utiliza con las definiciones anteriores, el código siguiente genera dos advertencias y un error:  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 Dos advertencias para la clase `A` se generan: uno para la declaración de la referencia de clase y otro para el constructor de clase.  
  
 El `Obsolete` atributo se puede utilizar sin argumentos, pero incluyendo una explicación de por qué el elemento está obsoleto y lo que se debe utilizar en su lugar, se recomienda.  
  
 El `Obsolete` atributo es un atributo de uso único y se puede aplicar a cualquier entidad que permita atributos. `Obsolete`es un alias para <xref:System.ObsoleteAttribute>.</xref:System.ObsoleteAttribute>  
  
##  <a name="Conditional"></a>Atributo condicional  
 El `Conditional` atributo hace que la ejecución de un método depende de un identificador de preprocesamiento. El `Conditional` atributo es un alias para <xref:System.Diagnostics.ConditionalAttribute>y se puede aplicar a un método o una clase de atributo</xref:System.Diagnostics.ConditionalAttribute>  
  
 En este ejemplo, `Conditional` se aplica a un método para habilitar o deshabilitar la presentación de información de diagnóstico específica del programa:  
  
```vb  
#Const TRACE_ON = True  
Imports System  
Imports System.Diagnostics  
Module TestConditionalAttribute  
    Public Class Trace  
        <Conditional("TRACE_ON")>   
        Public Shared Sub Msg(ByVal msg As String)  
            Console.WriteLine(msg)  
        End Sub  
  
    End Class  
  
    Sub Main()  
        Trace.Msg("Now in Main...")  
        Console.WriteLine("Done.")  
    End Sub  
End Module  
```  
  
 Si el `TRACE_ON` identificador no está definido, no se mostrará ningún resultado del seguimiento.  
  
 El `Conditional` a menudo se usa el atributo con el `DEBUG` identificador para habilitar el seguimiento y registro características para compilaciones de depuración pero no en lanzamiento, como esta:  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 Cuando se llama a un método marcado como condicional, la presencia o ausencia del símbolo de preprocesamiento especificado determina si la llamada se incluye o se omite. Si el símbolo está definido, la llamada se incluye; de lo contrario, se omite la llamada. Usando `Conditional` es un limpiador alternativa más elegante y menos propensa a errores que agregar métodos dentro `#if…#endif` bloques, similar al siguiente:  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 Un método condicional debe ser un método en una declaración de clase o struct y no debe tener un valor devuelto.  
  
### <a name="using-multiple-identifiers"></a>Usar varios identificadores  
 Si un método tiene varios `Conditional` atributos, se incluye una llamada al método si al menos uno de los símbolos condicionales está definido (es decir, los símbolos son lógicamente vinculados entre sí mediante el operador OR). En este ejemplo, la presencia de uno de ellos `A` o `B` dará como resultado de una llamada al método:  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 Para lograr el efecto de vinculación lógica de símbolos mediante el operador AND, puede definir métodos condicionales en serie. Por ejemplo, el segundo método se ejecutará sólo si ambos `A` y `B` se definen:  
  
```vb  
<Conditional("A")>   
Shared Sub DoIfA()  
    DoIfAandB()  
End Sub  
  
<Conditional("B")>   
Shared Sub DoIfAandB()  
    ' Code to execute when both A and B are defined...  
End Sub  
```  
  
### <a name="using-conditional-with-attribute-classes"></a>Uso de Conditional con clases de atributos  
 El `Conditional` atributo también se puede aplicar a una definición de clase de atributo. En este ejemplo, el atributo personalizado `Documentation` sólo agregar información a los metadatos si se define DEBUG.  
  
```vb  
<Conditional("DEBUG")>   
Public Class Documentation  
    Inherits System.Attribute  
    Private text As String  
    Sub New(ByVal doc_text As String)  
        text = doc_text  
    End Sub  
End Class  
  
Class SampleClass  
    ' This attribute will only be included if DEBUG is defined.  
    <Documentation("This method displays an integer.")>   
    Shared Sub DoWork(ByVal i As Integer)  
        System.Console.WriteLine(i)  
    End Sub  
End Class  
```  
  
##  <a name="CallerInfo"></a>Atributos de información del llamador  
 Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método. Puede obtener la ruta de acceso del código fuente, el número de línea en el código fuente y el nombre del miembro del llamador.  
  
 Para obtener información del autor de la llamada de miembros, use los atributos que se aplican a los parámetros opcionales. Cada parámetro opcional especifica un valor predeterminado. En la tabla siguiente se enumera los atributos de información del llamador que se definen en el <xref:System.Runtime.CompilerServices?displayProperty=fullName>espacio de nombres:</xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
|Atributo|Descripción|Tipo|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Ruta de acceso completa del archivo de código fuente que contiene el llamador. Esta es la ruta de acceso en tiempo de compilación.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Número de línea en el archivo de origen desde el que se llama al método.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Nombre de método o propiedad del llamador. Para obtener más información, consulte [información del llamador (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).|`String`|  
  
 Para obtener más información acerca de los atributos de información del llamador, consulte [información del llamador (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).  
  
##  <a name="VB"></a>Atributos de Visual Basic  
 En la tabla siguiente se enumera los atributos que son específicos de Visual Basic.  
  
|Atributo|Propósito|  
|---------------|-------------|  
|<xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute>|Indica al compilador que la clase debe exponerse como un objeto COM.|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute>|Permite a los miembros de módulo tener acceso utilizando sólo la calificación necesaria para el módulo.|  
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute>|Especifica el tamaño de una cadena de longitud fija en una estructura para utilizarla con el archivo de entrada y salida funciones.|  
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|Especifica el tamaño de una matriz fija en una estructura para utilizarla con el archivo de entrada y salida funciones.|  
  
### <a name="comclassattribute"></a>COMClassAttribute  
 Use `COMClassAttribute` para simplificar el proceso de creación de componentes COM desde Visual Basic. Los objetos COM son considerablemente distintos de los ensamblados de .NET Framework y sin `COMClassAttribute`, deberá seguir una serie de pasos para generar un objeto COM desde Visual Basic. Para las clases marcadas con `COMClassAttribute`, el compilador realiza muchos de estos pasos automáticamente.  
  
### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute  
 Use `HideModuleNameAttribute` para permitir que los miembros de módulo obtenerse utilizando sólo la calificación necesaria para el módulo.  
  
### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute  
 Use `VBFixedStringAttribute` para forzar a que Visual Basic para crear una cadena de longitud fija. Las cadenas son de longitud variable de forma predeterminada y este atributo es útil cuando se almacenan cadenas en archivos. El código siguiente se muestra cómo hacerlo:  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a>VBFixedArrayAttribute  
 Use `VBFixedArrayAttribute` para declarar matrices de tamaño fijo. Como las cadenas de Visual Basic, las matrices son de longitud variable de forma predeterminada. Este atributo es útil cuando se serializa o escribir datos en archivos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Guía de programación de Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Atributos](https://msdn.microsoft.com/library/5x6cd29c)   
 [Reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Acceso a atributos mediante reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
