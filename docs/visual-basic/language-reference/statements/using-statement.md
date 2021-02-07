---
description: 'Más información sobre: instrucción using (Visual Basic)'
title: Instrucción Using
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: fea77a441182b7c3ecac58d4fe7f1297a87f086c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740891"
---
# <a name="using-statement-visual-basic"></a>Using (Instrucción, Visual Basic)

Declara el principio de un `Using` bloque y, opcionalmente, adquiere los recursos del sistema que controla el bloque.

## <a name="syntax"></a>Sintaxis

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>Partes

|Término|Definición|  
|---|---|  
|`resourcelist`|Necesario si no se proporciona `resourceexpression` . Lista de uno o varios recursos del sistema que `Using` controla este bloque, separados por comas.|  
|`resourceexpression`|Necesario si no se proporciona `resourcelist` . Variable o expresión de referencia que hace referencia a un recurso del sistema que va a controlar este `Using` bloque.|  
|`statements`|Opcional. Bloque de instrucciones que `Using` ejecuta el bloque.|  
|`End Using`|Necesario. Finaliza la definición del `Using` bloque y desecha todos los recursos que controle.|  

 Cada recurso del `resourcelist` elemento tiene la sintaxis y las partes siguientes:

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 o bien

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>Elementos resourcelist

|Término|Definición|  
|---|---|  
|`resourcename`|Obligatorio. Variable de referencia que hace referencia a un recurso del sistema que `Using` controla el bloque.|  
|`New`|Obligatorio si la `Using` instrucción adquiere el recurso. Si ya ha adquirido el recurso, utilice la segunda alternativa de sintaxis.|  
|`resourcetype`|Necesario. La clase del recurso. La clase debe implementar la <xref:System.IDisposable> interfaz.|  
|`arglist`|Opcional. Lista de argumentos que se pasan al constructor para crear una instancia de `resourcetype` . Vea [lista de parámetros](parameter-list.md).|  
|`resourceexpression`|Necesario. Variable o expresión que hace referencia a un recurso del sistema que cumple los requisitos de `resourcetype` . Si usa la segunda alternativa de sintaxis, debe adquirir el recurso antes de pasar el control a la `Using` instrucción.|  
  
## <a name="remarks"></a>Observaciones

 A veces, el código requiere un recurso no administrado, como un identificador de archivo, un contenedor COM o una conexión SQL. Un `Using` bloque garantiza la eliminación de uno o varios de estos recursos cuando el código finaliza con ellos. Esto hace que estén disponibles para que los use otro código.

 Los recursos administrados son eliminados por el recolector de elementos no utilizados (GC) de .NET Framework sin necesidad de codificación adicional por su parte. No necesita un `Using` bloque para los recursos administrados. Sin embargo, todavía puede usar un `Using` bloque para forzar la eliminación de un recurso administrado en lugar de esperar al recolector de elementos no utilizados.

 Un `Using` bloque tiene tres partes: adquisición, uso y eliminación.

- La *adquisición* significa crear una variable e inicializarla para hacer referencia al recurso del sistema. La `Using` instrucción puede adquirir uno o más recursos, o bien puede adquirir exactamente un recurso antes de entrar en el bloque y suministrarlo a la `Using` instrucción. Si proporciona `resourceexpression` , debe adquirir el recurso antes de pasar el control a la `Using` instrucción.

- El *uso* significa tener acceso a los recursos y realizar acciones con ellos. Las instrucciones entre `Using` y `End Using` representan el uso de los recursos.

- La *eliminación* significa llamar al <xref:System.IDisposable.Dispose%2A> método en el objeto de `resourcename` . Esto permite que el objeto finalice correctamente sus recursos. La `End Using` instrucción desecha los recursos bajo el `Using` control del bloque.

## <a name="behavior"></a>Comportamiento

 Un `Using` bloque se comporta como una `Try` construcción... `Finally` en la que el `Try` bloque usa los recursos y el `Finally` bloque los desecha. Por este motivo, el `Using` bloque garantiza la eliminación de los recursos, independientemente de cómo salga del bloque. Esto es así incluso en el caso de una excepción no controlada, excepto para <xref:System.StackOverflowException> .

 El ámbito de cada variable de recurso adquirido por la `Using` instrucción se limita al `Using` bloque.

 Si especifica más de un recurso del sistema en la `Using` instrucción, el efecto es el mismo que si anidara `Using` bloques uno dentro de otro.

 Si `resourcename` es `Nothing` , no se realiza ninguna llamada a <xref:System.IDisposable.Dispose%2A> y no se inicia ninguna excepción.

## <a name="structured-exception-handling-within-a-using-block"></a>Control de excepciones estructurado dentro de un bloque Using

 Si necesita controlar una excepción que puede producirse en el `Using` bloque, puede agregarle una construcción completa `Try` ... `Finally` Si necesita controlar el caso en el que la `Using` instrucción no puede adquirir un recurso correctamente, puede comprobar si `resourcename` es `Nothing` .

## <a name="structured-exception-handling-instead-of-a-using-block"></a>Control de excepciones estructurado en lugar de un bloque Using

 Si necesita un control más preciso sobre la adquisición de los recursos o si necesita código adicional en el `Finally` bloque, puede volver a escribir el `Using` bloque como una `Try` construcción... `Finally` . En el ejemplo siguiente se muestran esqueleto `Try` y `Using` construcciones que son equivalentes en la adquisición y la eliminación de `resource` .

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
> El código dentro del `Using` bloque no debe asignar el objeto `resourcename` a otra variable. Al salir del `Using` bloque, el recurso se desecha y la otra variable no puede tener acceso al recurso al que señala.

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se crea un archivo denominado log.txt y se escriben dos líneas de texto en el archivo. En el ejemplo también se lee el mismo archivo y se muestran las líneas de texto:

 Dado que <xref:System.IO.TextWriter> las <xref:System.IO.TextReader> clases y implementan la <xref:System.IDisposable> interfaz, el código puede usar `Using` instrucciones para asegurarse de que el archivo se cierra correctamente después de las operaciones de escritura y lectura.

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>Vea también

- <xref:System.IDisposable>
- [Try...Catch...Finally (instrucción)](try-catch-finally-statement.md)
- [Procedimiento para deshacerse de un recurso del sistema](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
