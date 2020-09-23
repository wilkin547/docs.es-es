---
title: Información del llamador
ms.date: 07/20/2015
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
ms.openlocfilehash: 33c7367626d66d1db2705fc2882ca0780d1b867f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090357"
---
# <a name="caller-information-visual-basic"></a>Información del llamador (Visual Basic)

Mediante los atributos de información del llamador, se puede obtener información sobre el llamador de un método. Puede obtener la ruta de acceso al código fuente, el número de línea en el código fuente y el nombre de miembro del llamador. Esta información resulta útil para el seguimiento y la depuración, así como para crear herramientas de diagnóstico.  
  
 Para obtener esta información, se usan los atributos que se aplican a los parámetros opcionales, que tienen valores predeterminados. En la tabla siguiente se enumeran los atributos de información del llamador que se definen en el espacio de nombres <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:  
  
|Atributo|Descripción|Tipo|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Ruta de acceso completa del archivo de código fuente que contiene el llamador. Esta es la ruta de acceso en tiempo de compilación.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Número de línea en el archivo de código fuente en el que se llama al método.|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Método o nombre de propiedad del llamador. Vea [Nombres de miembro](#MEMBERNAMES) más adelante en este tema.|`String`|  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo utilizar atributos de información del llamador. En cada llamada al método `TraceMessage`, la información del llamador se sustituye como argumentos para los parámetros opcionales.  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a>Comentarios  

 Se debe especificar un valor predeterminado explícito para cada parámetro opcional. No se pueden aplicar atributos de información del llamador para los parámetros que no se especifican como opcionales.  
  
 Los atributos de información del llamador no crean un parámetro opcional, sino que influyen en el valor predeterminado que se pasa cuando se omite el argumento.  
  
 Los valores de información del llamador se emiten como literales en el lenguaje intermedio (IL) en tiempo de compilación. A diferencia de los resultados de la propiedad <xref:System.Exception.StackTrace%2A> para las excepciones, los resultados no se ven afectados por confusión.  
  
 Puede proporcionar explícitamente los argumentos opcionales para controlar la información del llamador u ocultarla.  
  
### <a name="member-names"></a><a name="MEMBERNAMES"></a> Nombres de miembro  

 Se puede utilizar el atributo `CallerMemberName` para evitar especificar el nombre de miembro como un argumento `String` para el método llamado. Mediante esta técnica, se evita el problema de que la **refactorización de cambio de nombre** no cambie los valores `String`. Esta ventaja es especialmente útil para las siguientes tareas:  
  
- Usar el seguimiento y las rutinas de diagnóstico.  
  
- Implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> al enlazar datos. Esta interfaz permite que la propiedad de un objeto notifique a un control enlazado que la propiedad ha cambiado, de forma que el control pueda mostrar información actualizada. Sin el atributo `CallerMemberName`, se debe especificar el nombre de propiedad como un literal.  
  
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

- [Atributos de Visual Basic](../../language-reference/attributes.md)
- [Common Attributes (Visual Basic)](attributes/common-attributes.md) (Atributos comunes [Visual Basic])
- [Parámetros opcionales](../language-features/procedures/optional-parameters.md)
- [Conceptos de programación (Visual Basic)](index.md)
