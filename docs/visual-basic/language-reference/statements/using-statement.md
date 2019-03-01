---
title: Using (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 1cf0772bf4e9a77474849c59454617261475fa76
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966091"
---
# <a name="using-statement-visual-basic"></a>Using (Instrucción, Visual Basic)
Declara el principio de un `Using` bloquear y, opcionalmente, adquiere los recursos del sistema que controla el bloque.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|---|---|  
|`resourcelist`|Obligatorio si no se proporciona `resourceexpression`. Lista de uno o más recursos del sistema que este `Using` Bloquear controles, separados por comas.|  
|`resourceexpression`|Obligatorio si no se proporciona `resourcelist`. Variable de referencia o una expresión que hace referencia a un recurso del sistema que estén controladas por esto `Using` bloque.|  
|`statements`|Opcional. Bloque de instrucciones que el `Using` bloquear ejecuciones.|  
|`End Using`|Obligatorio. Termina la definición de la `Using` bloque y elimina todos los recursos que controla.|  
  
 Cada recurso en el `resourcelist` parte tiene la sintaxis y las partes siguientes:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 O bien  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>Partes de resourceList  
  
|Término|Definición|  
|---|---|  
|`resourcename`|Obligatorio. Variable de referencia que hace referencia a un recurso del sistema que la `Using` Bloquear controles.|  
|`New`|Es necesario si la `Using` instrucción adquiere el recurso. Si ya ha adquirido el recurso, use la segunda alternativa de sintaxis.|  
|`resourcetype`|Obligatorio. La clase del recurso. La clase debe implementar la <xref:System.IDisposable> interfaz.|  
|`arglist`|Opcional. Lista de argumentos que se pasa al constructor para crear una instancia de `resourcetype`. Consulte [Lista_de_parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Obligatorio. Variable o expresión que hace referencia a un recurso del sistema que cumpla los requisitos de `resourcetype`. Si usa la segunda alternativa de sintaxis, debe adquirir el recurso antes de pasar el control a la `Using` instrucción.|  
  
## <a name="remarks"></a>Comentarios  
 A veces el código requiere un recurso no administrado, como un identificador de archivo, un contenedor COM o una conexión SQL. Un `Using` bloque garantiza la eliminación de uno o varios de estos recursos cuando el código haya terminado con ellos. Esto pone a disposición para otro código para usar.  
  
 Los recursos administrados se eliminan mediante el recolector de elementos no utilizados (GC) de .NET Framework sin ninguna codificación adicional por su parte. No es necesario un `Using` bloque para los recursos administrados. Sin embargo, todavía puede usar un `Using` bloque para forzar la eliminación de un recurso administrado en lugar de esperar el recolector de elementos no utilizados.  
  
 Un `Using` bloque tiene tres partes: adquisición, uso y eliminación.  
  
-   *Adquisición* significa crear una variable e inicializarla para hacer referencia al recurso del sistema. El `Using` instrucción puede adquirir uno o más recursos, o puede adquirir exactamente un recurso antes de entrar en el bloque y proporcionarlo a la `Using` instrucción. Si proporciona `resourceexpression`, debe adquirir el recurso antes de pasar el control a la `Using` instrucción.  
  
-   *Uso* significa tener acceso a los recursos y realizar acciones con ellos. Las instrucciones entre `Using` y `End Using` representan el uso de los recursos.  
  
-   *Eliminación* significa llamar a la <xref:System.IDisposable.Dispose%2A> método en el objeto en `resourcename`. Esto permite que el objeto terminar limpiamente sus recursos. El `End Using` instrucción elimina los recursos en el `Using` control del bloque.  
  
## <a name="behavior"></a>Comportamiento  
 Un `Using` bloque se comporta como un `Try`... `Finally` construcción en el que el `Try` bloque usa los recursos y la `Finally` bloque elimina de ellos. Por este motivo, la `Using` bloque garantiza la eliminación de los recursos, independientemente de cómo salga el bloque. Esto es cierto incluso si se produce una excepción no controlada, excepto para un <xref:System.StackOverflowException>.  
  
 El ámbito de cada variable de recursos adquirido por la `Using` instrucción está limitada a la `Using` bloque.  
  
 Si especifica más de un recurso del sistema en el `Using` instrucción, el efecto es el mismo como si anida `Using` bloquea uno dentro de otra.  
  
 Si `resourcename` es `Nothing`, ninguna llamada a <xref:System.IDisposable.Dispose%2A> se realiza, y se produce ninguna excepción.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Control dentro de un bloque Using estructurado de excepciones  
 Si tiene que controlar una excepción que se produzcan dentro de la `Using` bloque, puede agregar una completa `Try`... `Finally` construcción a él. Si necesita controlar el caso donde la `Using` instrucción no se realiza correctamente al adquirir un recurso, puede probar para ver si `resourcename` es `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>En lugar de un bloque Using de control de excepciones estructurado  
 Si necesita un mayor control sobre la adquisición de los recursos, o si necesita código adicional en el `Finally` bloque, puede volver a escribir el `Using` bloquear como un `Try`... `Finally` construcción. El ejemplo siguiente muestra el esqueleto `Try` y `Using` construcciones que son equivalentes en la adquisición y eliminación de `resource`.  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  El código dentro de la `Using` bloque no debería asignar el objeto en `resourcename` a otra variable. Al salir el `Using` bloque, el recurso se elimina y la otra variable no puede acceder al recurso al que señala.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un archivo denominado log.txt y escribe dos líneas de texto en el archivo. El ejemplo también lee ese mismo archivo y muestra las líneas de texto.  
  
 Dado que el <xref:System.IO.TextWriter> y <xref:System.IO.TextReader> clases implementan la <xref:System.IDisposable> interfaz, puede usar el código `Using` instrucciones para asegurarse de que el archivo se cierra después de la escritura y las operaciones de lectura correctamente.  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.IDisposable>
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Cómo: Deshacerse de un recurso del sistema](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
