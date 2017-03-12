---
title: "La expresi&#243;n llama de forma recursiva a la propiedad contenedora &#39;&lt;nombre de propiedad&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42026"
  - "BC42026"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42026"
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# La expresi&#243;n llama de forma recursiva a la propiedad contenedora &#39;&lt;nombre de propiedad&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una instrucción del procedimiento `Set` de una definición de propiedad almacena un valor en el nombre de la propiedad.  
  
 El enfoque recomendado para conservar el valor de una propiedad consiste en definir una variable `Private` en el contenedor de la propiedad y utilizarlo tanto los procedimientos `Get` como `Set`.  El procedimiento `Set` debería almacenar entonces el valor de entrada en esta variable `Private`.  
  
 El procedimiento `Get` se comporta como un procedimiento `Function`, de manera que puede asignar un valor al nombre de propiedad y devolver el control cuando se encuentra la instrucción `End Get`.  El enfoque recomendado, sin embargo, es incluir la variable `Private` como el valor de una [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 El procedimiento `Set` se comporta como un procedimiento `Sub`, que no devuelve un valor.  Por consiguiente, el procedimiento o el nombre de propiedad no tiene ningún significado especial dentro de un procedimiento `Set` y no se pueden almacenar valores en él.  
  
 El ejemplo siguiente muestra el enfoque que puede producir este error, seguido por el enfoque recomendado.  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratar las advertencias como errores, consulte [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42026  
  
### Para corregir este error  
  
-   Escriba de nuevo la definición de propiedad para utilizar el enfoque recomendado como se muestra en el ejemplo anterior.  
  
## Vea también  
 [Procedimientos de propiedad](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Set \(Instrucción\)](../../../visual-basic/language-reference/statements/set-statement.md)