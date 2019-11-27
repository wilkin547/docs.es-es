---
title: Using (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 6ec0e228b3898f66f27e322b5db2dd7f3bf3d7d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352759"
---
# <a name="using-statement-visual-basic"></a>Using (Instrucción, Visual Basic)

Declara el principio de un bloque `Using` y, opcionalmente, adquiere los recursos del sistema que controla el bloque.

## <a name="syntax"></a>Sintaxis

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>Elementos

|Término|Definición|  
|---|---|  
|`resourcelist`|Necesario si no se proporciona `resourceexpression`. Lista de uno o varios recursos del sistema que este `Using` bloque controla, separados por comas.|  
|`resourceexpression`|Necesario si no se proporciona `resourcelist`. Variable o expresión de referencia que hace referencia a un recurso del sistema para que lo controle este bloque `Using`.|  
|`statements`|Opcional. Bloque de instrucciones que ejecuta el bloque `Using`.|  
|`End Using`|Obligatorio. Finaliza la definición del bloque de `Using` y desecha todos los recursos que controla.|  

 Cada recurso del elemento `resourcelist` tiene la sintaxis y las partes siguientes:

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 O bien,

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>Elementos resourcelist

|Término|Definición|  
|---|---|  
|`resourcename`|Obligatorio. Variable de referencia que hace referencia a un recurso del sistema que el bloque `Using` controla.|  
|`New`|Obligatorio si la instrucción `Using` adquiere el recurso. Si ya ha adquirido el recurso, utilice la segunda alternativa de sintaxis.|  
|`resourcetype`|Obligatorio. La clase del recurso. La clase debe implementar la interfaz <xref:System.IDisposable>.|  
|`arglist`|Opcional. Lista de argumentos que se pasan al constructor para crear una instancia de `resourcetype`. Vea [lista de parámetros](parameter-list.md).|  
|`resourceexpression`|Obligatorio. Variable o expresión que hace referencia a un recurso del sistema que cumple los requisitos de `resourcetype`. Si usa la segunda alternativa de sintaxis, debe adquirir el recurso antes de pasar el control a la instrucción `Using`.|  
  
## <a name="remarks"></a>Comentarios

 A veces, el código requiere un recurso no administrado, como un identificador de archivo, un contenedor COM o una conexión SQL. Un bloque `Using` garantiza la eliminación de uno o más recursos de este tipo cuando el código finaliza con ellos. Esto hace que estén disponibles para que los use otro código.

 Los recursos administrados son eliminados por el recolector de elementos no utilizados (GC) de .NET Framework sin necesidad de codificación adicional por su parte. No necesita un bloque `Using` para los recursos administrados. Sin embargo, todavía puede usar un bloque `Using` para forzar la eliminación de un recurso administrado en lugar de esperar al recolector de elementos no utilizados.

 Un bloque `Using` tiene tres partes: adquisición, uso y eliminación.

- La *adquisición* significa crear una variable e inicializarla para hacer referencia al recurso del sistema. La instrucción `Using` puede adquirir uno o más recursos, o bien puede adquirir exactamente un recurso antes de entrar en el bloque y suministrarlo a la instrucción `Using`. Si proporciona `resourceexpression`, debe adquirir el recurso antes de pasar el control a la instrucción `Using`.

- El *uso* significa tener acceso a los recursos y realizar acciones con ellos. Las instrucciones entre `Using` y `End Using` representan el uso de los recursos.

- La *eliminación* significa llamar al método <xref:System.IDisposable.Dispose%2A> en el objeto en `resourcename`. Esto permite que el objeto finalice correctamente sus recursos. La instrucción `End Using` desecha los recursos del control del bloque de `Using`.

## <a name="behavior"></a>Comportamiento

 Un bloque de `Using` se comporta como una construcción `Try`...`Finally` en la que el bloque de `Try` utiliza los recursos y el bloque de `Finally` los desecha. Por este motivo, el bloque de `Using` garantiza la eliminación de los recursos, con independencia de cómo salga del bloque. Esto es así incluso en el caso de una excepción no controlada, excepto para un <xref:System.StackOverflowException>.

 El ámbito de cada variable de recurso adquirido por la instrucción `Using` se limita al bloque `Using`.

 Si especifica más de un recurso del sistema en la instrucción `Using`, el efecto es el mismo que si anidara `Using` bloques uno dentro de otro.

 Si `resourcename` es `Nothing`, no se realiza ninguna llamada a <xref:System.IDisposable.Dispose%2A> y no se produce ninguna excepción.

## <a name="structured-exception-handling-within-a-using-block"></a>Control de excepciones estructurado dentro de un bloque Using

 Si necesita controlar una excepción que puede producirse en el bloque `Using`, puede Agregar a ella una construcción `Try`completa...`Finally`. Si necesita controlar el caso en el que la instrucción `Using` no tiene éxito al adquirir un recurso, puede probar si `resourcename` está `Nothing`.

## <a name="structured-exception-handling-instead-of-a-using-block"></a>Control de excepciones estructurado en lugar de un bloque Using

 Si necesita un control más preciso sobre la adquisición de los recursos o si necesita código adicional en el bloque `Finally`, puede volver a escribir el bloque de `Using` como una construcción `Try`...`Finally`. En el ejemplo siguiente se muestra el esqueleto `Try` y `Using` construcciones que son equivalentes en la adquisición y la eliminación de `resource`.

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
> El código dentro del bloque `Using` no debe asignar el objeto de `resourcename` a otra variable. Al salir del bloque `Using`, el recurso se desecha y la otra variable no puede tener acceso al recurso al que señala.

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se crea un archivo denominado log. txt y se escriben dos líneas de texto en el archivo. En el ejemplo también se lee el mismo archivo y se muestran las líneas de texto:

 Dado que las clases <xref:System.IO.TextWriter> y <xref:System.IO.TextReader> implementan la interfaz <xref:System.IDisposable>, el código puede usar instrucciones `Using` para asegurarse de que el archivo se cierra correctamente después de las operaciones de escritura y lectura.

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>Vea también

- <xref:System.IDisposable>
- [Try...Catch...Finally (instrucción)](try-catch-finally-statement.md)
- [Deshacerse de un recurso del sistema](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
