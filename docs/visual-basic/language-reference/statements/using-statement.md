---
title: "Using (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.using"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "eliminación de recursos"
  - "recursos [Visual Basic], desechar"
  - "Try...Catch...Finally (instrucciones), equivalente a la instrucción Using"
  - "Using (instrucción)"
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 36
caps.handback.revision: 36
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Using (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Declara el principio de un bloque `Using` y, opcionalmente, adquiere los recursos del sistema que controla el bloque.  
  
## Sintaxis  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`resourcelist`|Obligatorio si no se proporciona una expresión `resourceexpression`.  Lista de uno o más recursos del sistema que controles de este bloque `Using` , separados por comas.|  
|`resourceexpression`|Obligatorio si no se proporciona una `resourcelist`.  Variable de referencia o expresión que hace referencia a un recurso del sistema que va a controlar este bloque `Using`.|  
|`statements`|Opcional.  Bloque de instrucciones que ejecuta el bloque `Using`.|  
|`End Using`|Requerido.  Finaliza la definición del bloque `Using` y desecha todos los recursos que controla.|  
  
 Cada recurso incluido en la parte `resourcelist` tiene la siguiente sintaxis y partes:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 O bien  
  
 `resourcename As resourcetype = resourceexpression`  
  
## Partes de resourcelist  
  
|||  
|-|-|  
|Término|Definición|  
|`resourcename`|Requerido.  Variable de referencia que hace referencia a un recurso del sistema que controla el bloque `Using`.|  
|`New`|Obligatorio si la instrucción `Using` adquiere el recurso.  Si ya ha adquirido el recurso, utilice la segunda alternativa de la sintaxis.|  
|`resourcetype`|Requerido.  Clase del recurso.  La clase debe implementar la interfaz <xref:System.IDisposable>.|  
|`arglist`|Opcional.  Lista de argumentos que está pasando al constructor para crear una instancia de `resourcetype`.  Vea [Lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Requerido.  Variable o expresión que hace referencia a un recurso del sistema que satisface los requisitos de `resourcetype`.  Si utiliza la segunda alternativa de la sintaxis, debe adquirir el recurso antes de pasar el control a la instrucción `Using`.|  
  
## Comentarios  
 A veces su código requiere un recurso no administrado, como un identificador de archivos, un contenedor COM o una conexión SQL.  Un bloque `Using` garantiza la eliminación de uno o más de tales recursos cuando su código termina de usarlos.  Esto los pone a disposición de otro código para que los pueda utilizar.  
  
 Los recursos administrados se eliminan mediante el recolector de elementos no utilizados \(GC\) de .NET Framework sin necesidad de código adicional por su parte.  Para los recursos administrados no es necesario utilizar ningún bloque `Using`.  Sin embargo, todavía puede utilizar un bloque `Using` para forzar la eliminación de un recurso administrado en lugar de esperar al recolector de elementos no utilizados.  
  
 Un bloque `Using` tiene tres partes: adquisición, uso y eliminación.  
  
-   *Adquisición* significa crear una variable e inicializarla para hacer referencia al recurso del sistema.  La instrucción `Using` puede adquirir uno o más recursos, o bien, puede adquirir exactamente un recurso antes de entrar en el bloque y proporcionarlo a la instrucción `Using`.  Si proporciona una `resourceexpression`, debe adquirir el recurso antes de pasar el control a la instrucción `Using`.  
  
-   *Uso* significa tener acceso a los recursos y realizar acciones con ellos.  Las instrucciones entre `Using` y `End Using` representan el uso de los recursos.  
  
-   *Eliminación* significa llamar al método <xref:System.IDisposable.Dispose%2A> en el objeto de `resourcename`.  Esto permite al objeto finalizar limpiamente sus recursos.  La instrucción `End Using` elimina los recursos bajo el control del bloque `Using`.  
  
## Comportamiento  
 Un bloque `Using` se comporta como una construcción `Try`...`Finally` en la que el bloque `Try` utiliza los recursos y el bloque `Finally` los desecha.  Gracias a esto, el bloque `Using` garantiza la eliminación de los recursos, independientemente de cómo salga del bloque.  Esto es cierto incluso en el caso de una excepción no controlada, excepto para una excepción <xref:System.StackOverflowException>.  
  
 El ámbito de cada variable de recurso adquirido por la instrucción `Using` se limita al bloque `Using`.  
  
 Si especifica más de un recurso de sistema en la instrucción `Using`, el efecto es el mismo que si anidara unos bloques `Using` dentro de otros.  
  
 Si `resourcename` es `Nothing`, no se realiza ninguna llamada a <xref:System.IDisposable.Dispose%2A> , y no se produce ninguna excepción.  
  
## Control de excepción estructurada dentro de un bloque Using  
 Si necesita controlar una excepción que podría aparecer dentro del bloque `Using`, puede agregarle una construcción `Try`...`Finally`.  Si necesita controlar el caso en el que la instrucción `Using` no consigue adquirir un recurso, puede comprobar si `resourcename` es `Nothing`.  
  
## Control de excepción estructurada en lugar de un bloque Using  
 Si necesita un control más preciso sobre la adquisición de los recursos, o si necesita código adicional en el bloque `Finally`, puede volver a escribir el bloque `Using` como una construcción `Try`...`Finally`.  El ejemplo siguiente muestra una estructura `Try` y construcciones `Using` que son equivalentes en la adquisición y eliminación de `resource`.  
  
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
>  El código situado dentro del bloque `Using` no debería asignar a otra variable el objeto de `resourcename`.  Cuando sale del bloque `Using`, se elimina el recurso y la otra variable no puede tener acceso al recurso al que señala.  
  
## Ejemplo  
 El ejemplo siguiente se crea un archivo denominado log.txt y escribe dos líneas de texto al archivo.  El ejemplo lee también que el mismo archivo y muestra las líneas de texto.  
  
 Dado que las clases <xref:System.IO.TextWriter> y <xref:System.IO.TextReader> implementan la interfaz <xref:System.IDisposable> , el código puede utilizar las instrucciones `Using` para asegurarse de que el archivo correctamente se cierra después de escribir y de las operaciones de lectura.  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## Vea también  
 <xref:System.IDisposable>   
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Cómo: Deshacerse de un recurso del sistema](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)