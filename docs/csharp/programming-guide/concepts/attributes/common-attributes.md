---
title: Atributos comunes (C#)
ms.date: 07/20/2015
ms.assetid: 785a0526-6c0e-4599-8c61-ccdc88dd9965
ms.openlocfilehash: 7988dad410c6e51869ec9d7e40d94e874443a5f8
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595461"
---
# <a name="common-attributes-c"></a>Atributos comunes (C#)
En este tema se describen los atributos que más se usan en los programas de C#.  
  
- [Atributos globales](#Global)  
  
- [Atributo Obsolete](#Obsolete)  
  
- [Atributo Conditional](#Conditional)  
  
- [Atributos de información del llamador](#CallerInfo)  
  
## <a name="Global"></a> Atributos globales  
 La mayoría de los atributos se aplican a elementos específicos del lenguaje, como las clases o los métodos, aunque algunos atributos son globales (se aplican a todo un ensamblado o módulo). Por ejemplo, el atributo <xref:System.Reflection.AssemblyVersionAttribute> se puede usar para insertar información de versión en un ensamblado, como en este ejemplo:  
  
```csharp  
[assembly: AssemblyVersion("1.0.0.0")]  
```  
  
 Los atributos globales aparecen en el código fuente después de cualquier directiva `using` de nivel superior y antes de cualquier declaración de espacio de nombres, módulo o tipo. Los atributos globales pueden aparecer en varios archivos de código fuente, pero estos archivos se deben compilar en un solo paso de compilación. En los proyectos de C#, los atributos globales se colocan en el archivo AssemblyInfo.cs.  
  
 Los atributos de ensamblado son valores que proporcionan información sobre un ensamblado. Se dividen en las siguientes categorías:  
  
- Atributos de identidad del ensamblado  
  
- Atributos informativos  
  
- Atributos de manifiesto del ensamblado  
  
### <a name="assembly-identity-attributes"></a>Atributos de identidad del ensamblado  
 Tres atributos, con un nombre seguro (si procede), determinan la identidad de un ensamblado: nombre, versión y referencia cultural. Estos atributos forman el nombre completo del ensamblado y son necesarios cuando se hace referencia a este en el código. Puede establecer la versión y la referencia cultural de un ensamblado mediante atributos, pero el valor de nombre lo establece el compilador, el IDE de Visual Studio en el [cuadro de diálogo de información de ensamblado](/visualstudio/ide/reference/assembly-information-dialog-box) o la herramienta Assembly Linker (Al.exe) cuando se crea el ensamblado, a partir del archivo que contiene el manifiesto del ensamblado. El atributo <xref:System.Reflection.AssemblyFlagsAttribute> especifica si pueden coexistir varias copias del ensamblado.  
  
 En la siguiente tabla se muestran los atributos de identidad.  
  
|Atributo|Propósito|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|Describe completamente la identidad de un ensamblado.|  
|<xref:System.Reflection.AssemblyVersionAttribute>|Especifica la versión de un ensamblado.|  
|<xref:System.Reflection.AssemblyCultureAttribute>|Especifica la cultura que admite el ensamblado.|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|Especifica si un ensamblado admite la ejecución en paralelo en el mismo equipo, en el mismo proceso o en el mismo dominio de aplicación.|  
  
### <a name="informational-attributes"></a>Atributos informativos  
 Puede utilizar atributos informativos para proporcionar información adicional de la compañía o de producto para un ensamblado. En la tabla siguiente se muestran los atributos informativos definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.  
  
|Atributo|Propósito|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute>|Define un atributo personalizado que especifica un nombre de producto para un manifiesto del ensamblado.|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Define un atributo personalizado que especifica una marca comercial para un manifiesto del ensamblado.|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Define un atributo personalizado que especifica una versión informativa para un manifiesto del ensamblado.|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|Define un atributo personalizado que especifica un nombre de compañía para un manifiesto del ensamblado.|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Define un atributo personalizado que especifica un copyright para un manifiesto del ensamblado.|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Indica al compilador que use un número de versión específico para el recurso de versión de archivo Win32.|  
|<xref:System.CLSCompliantAttribute>|Indica si el ensamblado es compatible con Common Language Specification (CLS).|  
  
### <a name="assembly-manifest-attributes"></a>Atributos de manifiesto del ensamblado  
 Puede usar los atributos de manifiesto del ensamblado para proporcionar información en el manifiesto del ensamblado (título, descripción, alias predeterminado y configuración). En la tabla siguiente se muestran los atributos de manifiesto del ensamblado definidos en el espacio de nombres <xref:System.Reflection?displayProperty=nameWithType>.  
  
|Atributo|Propósito|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|Define un atributo personalizado que especifica un título de ensamblado para un manifiesto del ensamblado.|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Define un atributo personalizado que especifica una descripción de ensamblado para un manifiesto del ensamblado.|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Define un atributo personalizado que especifica una configuración de ensamblado (por ejemplo, comercial o depuración) para un manifiesto del ensamblado.|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Define un alias descriptivo predeterminado para un manifiesto del ensamblado.|  
  
## <a name="Obsolete"></a> Atributo Obsolete  
 El atributo `Obsolete` marca una entidad del programa como una entidad cuyo uso ya no se recomienda. Cada uso de una entidad marcada como obsoleta generará posteriormente una advertencia o un error, en función de la configuración del atributo. Por ejemplo:  
  
```csharp  
[System.Obsolete("use class B")]  
class A  
{  
    public void Method() { }  
}  
class B  
{  
    [System.Obsolete("use NewMethod", true)]  
    public void OldMethod() { }  
    public void NewMethod() { }  
}  
```  
  
 En este ejemplo, el atributo `Obsolete` se aplica a la clase `A` y al método `B.OldMethod`. Dado que el segundo argumento del constructor de atributos aplicado a `B.OldMethod` está establecido en `true`, este método producirá un error del compilador, mientras que, si se usa la clase `A`, solo se generará una advertencia. En cambio, si se llama a `B.NewMethod`, no se generará ninguna advertencia o error.  
  
 La cadena proporcionada como primer argumento al constructor de atributos se mostrará como parte de la advertencia o error. Por ejemplo, al usarla con las definiciones anteriores, el código siguiente genera dos advertencias y un error:  
  
```csharp  
// Generates 2 warnings:  
// A a = new A();  
  
// Generate no errors or warnings:  
B b = new B();  
b.NewMethod();  
  
// Generates an error, terminating compilation:  
// b.OldMethod();  
```  
  
 Se generan dos advertencias para la clase `A`: una para la declaración de la referencia de clase y otra para el constructor de clases.  
  
 El atributo `Obsolete` se puede usar sin argumentos, aunque se recomienda incluir una explicación de por qué el elemento está obsoleto y qué se debe usar en su lugar.  
  
 El atributo `Obsolete` es un atributo de uso único y se puede aplicar a cualquier entidad que admita atributos. `Obsolete` es un alias de <xref:System.ObsoleteAttribute>.  
  
## <a name="Conditional"></a> Atributo Conditional  
 El atributo `Conditional` hace que la ejecución de un método dependa de un identificador de preprocesamiento. El atributo `Conditional` es un alias de <xref:System.Diagnostics.ConditionalAttribute> y se puede aplicar a un método o a una clase de atributo.  
  
 En este ejemplo, `Conditional` se aplica a un método para habilitar o deshabilitar la visualización de información de diagnóstico específica del programa:  
  
```csharp  
#define TRACE_ON  
using System;  
using System.Diagnostics;  
  
public class Trace  
{  
    [Conditional("TRACE_ON")]  
    public static void Msg(string msg)  
    {  
        Console.WriteLine(msg);  
    }  
}  
  
public class ProgramClass  
{  
    static void Main()  
    {  
        Trace.Msg("Now in Main...");  
        Console.WriteLine("Done.");  
    }  
}  
```  
  
 Si el identificador `TRACE_ON` no está definido, no se mostrará ningún resultado del seguimiento.  
  
 El atributo `Conditional` se suele usar con el identificador `DEBUG` para habilitar las funciones de seguimiento y de registro para las compilaciones de depuración (pero no en las compilaciones de versión), como en este ejemplo:  
  
```csharp  
[Conditional("DEBUG")]  
static void DebugMethod()  
{  
}  
```  
  
 Al llamar a un método marcado como condicional, la presencia o ausencia del símbolo de preprocesamiento especificado determina si se incluye o se omite la llamada. Si el símbolo está definido, se incluye la llamada; de lo contrario, se omite la llamada. Usar `Conditional` es una alternativa más limpia, más elegante y menos propensa a generar errores para agregar métodos dentro de los bloques `#if…#endif`, como en el siguiente ejemplo:  
  
```csharp  
#if DEBUG  
    void ConditionalMethod()  
    {  
    }  
#endif  
```  
  
 Los métodos condicionales deben ser métodos de una declaración de clase o struct y no deben tener ningún valor devuelto.  
  
### <a name="using-multiple-identifiers"></a>Usar varios identificadores  
 Si un método tiene varios atributos `Conditional`, se incluye una llamada al método si al menos uno de los símbolos condicionales está definido (es decir, si los símbolos están vinculados lógicamente entre sí mediante el operador OR). En este ejemplo, la presencia de `A` o de `B` dará como resultado una llamada al método:  
  
```csharp  
[Conditional("A"), Conditional("B")]  
static void DoIfAorB()  
{  
    // ...  
}  
```  
  
 Para lograr el efecto de una vinculación lógica de símbolos mediante el operador AND, puede definir métodos condicionales en serie. Por ejemplo, el segundo método que se muestra a continuación solo se ejecutará si tanto `A` como `B` están definidos:  
  
```csharp
[Conditional("A")]  
static void DoIfA()  
{  
    DoIfAandB();  
}  
  
[Conditional("B")]  
static void DoIfAandB()  
{  
    // Code to execute when both A and B are defined...  
}  
```  
  
### <a name="using-conditional-with-attribute-classes"></a>Usar Conditional con clases de atributos  
 El atributo `Conditional` también se puede aplicar a una definición de clase de atributo. En este ejemplo, el atributo personalizado `Documentation` solo agregará información a los metadatos si se define DEBUG.  
  
```csharp  
[Conditional("DEBUG")]  
public class Documentation : System.Attribute  
{  
    string text;  
  
    public Documentation(string text)  
    {  
        this.text = text;  
    }  
}  
  
class SampleClass  
{  
    // This attribute will only be included if DEBUG is defined.  
    [Documentation("This method displays an integer.")]  
    static void DoWork(int i)  
    {  
        System.Console.WriteLine(i.ToString());  
    }  
}  
```  
  
## <a name="CallerInfo"></a> Atributos de información del llamador  
 Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método. Puede obtener la ruta de acceso al código fuente, el número de línea del código fuente y el nombre del miembro del llamador.  
  
 Para obtener la información del llamador del miembro, use los atributos que se aplican a los parámetros opcionales. Cada parámetro opcional especifica un valor predeterminado. En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:  
  
|Atributo|DESCRIPCIÓN|Tipo|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Ruta de acceso completa del archivo de código fuente que contiene el llamador. Esta es la ruta de acceso en tiempo de compilación.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Número de línea del archivo de código fuente desde el que se llama al método.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Nombre de método o de propiedad del llamador. Para obtener más información, vea [Información del llamador (C#)](../caller-information.md).|`String`|  
  
 Para obtener más información sobre los atributos de información del llamador, vea [Información del llamador (C#)](../caller-information.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Guía de programación de C#](../../index.md)
- [Atributos](../../../../standard/attributes/index.md)
- [Reflexión (C#)](../reflection.md)
- [Acceder a atributos mediante reflexión (C#)](./accessing-attributes-by-using-reflection.md)
