---
title: "Información del llamador (C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ffad3d24-2fb7-4641-9124-53b5bc91d339
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 05c153afd502da1f290b3bc36460ded27789e21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information-c"></a>Información del llamador (C#)
Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método. Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador. Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.  
  
 Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados. En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:  
  
|Atributo|Descripción|Tipo|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Ruta de acceso completa del archivo de código fuente que contiene el llamador. Esta es la ruta de acceso en tiempo de compilación.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Número de línea en el archivo de código fuente en el que se llama al método.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Método o nombre de propiedad del llamador. Vea [Nombres de miembro](#MEMBERNAMES) más adelante en este tema.|`String`|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar atributos de información del llamador. En cada llamada al método `TraceMessage`, la información del llamador se sustituye como argumentos para los parámetros opcionales.  
  
```csharp  
public void DoProcessing()  
{  
    TraceMessage("Something happened.");  
}  
  
public void TraceMessage(string message,  
        [System.Runtime.CompilerServices.CallerMemberName] string memberName = "",  
        [System.Runtime.CompilerServices.CallerFilePath] string sourceFilePath = "",  
        [System.Runtime.CompilerServices.CallerLineNumber] int sourceLineNumber = 0)  
{  
    System.Diagnostics.Trace.WriteLine("message: " + message);  
    System.Diagnostics.Trace.WriteLine("member name: " + memberName);  
    System.Diagnostics.Trace.WriteLine("source file path: " + sourceFilePath);  
    System.Diagnostics.Trace.WriteLine("source line number: " + sourceLineNumber);  
}  
  
// Sample Output:  
//  message: Something happened.  
//  member name: DoProcessing  
//  source file path: c:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoCS\CallerInfoCS\Form1.cs  
//  source line number: 31  
```  
  
## <a name="remarks"></a>Comentarios  
 Se debe especificar un valor predeterminado explícito para cada parámetro opcional. No se pueden aplicar atributos de información del llamador para los parámetros que no se especifican como opcionales.  
  
 Los atributos de información del llamador no crean un parámetro opcional, sino que influyen en el valor predeterminado que se pasa cuando se omite el argumento.  
  
 Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación. A diferencia de los resultados de la propiedad <xref:System.Exception.StackTrace%2A> para las excepciones, los resultados no se ven afectados por confusión.  
  
 Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.  
  
###  <a name="MEMBERNAMES"></a> Nombres de miembro  
 Se puede utilizar el atributo `CallerMemberName` para evitar especificar el nombre de miembro como un argumento `String` para el método llamado. Mediante esta técnica, se evita el problema de que la **refactorización de cambio de nombre** no cambie los valores `String`. Esta ventaja es especialmente útil para las siguientes tareas:  
  
-   Usar el seguimiento y las rutinas de diagnóstico.  
  
-   Implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> al enlazar datos. Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada. Sin el atributo `CallerMemberName`, se debe especificar el nombre de propiedad como un literal.  
  
 En el gráfico siguiente se muestran los nombres de miembro que se devuelven cuando se utiliza el atributo `CallerMemberName`.  
  
|Las llamadas se producen en|Resultado del nombre de miembro|  
|-------------------------|------------------------|  
|Método, propiedad o evento|Nombre del método, propiedad o evento en el que se originó la llamada.|  
|Constructor|Cadena ".ctor"|  
|Constructor estático|Cadena ".cctor"|  
|Destructor|Cadena "Finalize"|  
|Conversiones u operadores definidos por el usuario|Nombre generado para el miembro, por ejemplo, "op_Addition".|  
|Constructor de atributo|Nombre del miembro al que se aplica el atributo. Si el atributo es cualquier elemento dentro de un miembro (como un parámetro, un valor devuelto o un parámetro de tipo genérico), el resultado es el nombre del miembro asociado a este elemento.|  
|Ningún miembro contenedor (por ejemplo, nivel de ensamblado o atributos que se aplican a tipos)|El valor predeterminado del parámetro opcional.|  
  
## <a name="see-also"></a>Vea también  
 [Atributos (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)  
 [Atributos comunes (C#)](../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
 [Argumentos opcionales y con nombre](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
 [Conceptos de programación (C#)](../../../csharp/programming-guide/concepts/index.md)
