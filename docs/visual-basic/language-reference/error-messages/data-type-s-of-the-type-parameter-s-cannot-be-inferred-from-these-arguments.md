---
title: "Los tipos de datos de los par&#225;metros de tipo no se pueden inferir de estos argumentos | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36644"
  - "bc36647"
  - "vbc36647"
  - "vbc36644"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36644"
  - "BC36647"
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Los tipos de datos de los par&#225;metros de tipo no se pueden inferir de estos argumentos
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los tipos de datos de los parámetros de tipo no se pueden inferir de estos argumentos.Al especificar los tipos de datos explícitamente, se podría corregir este error.  
  
 Este error aparece al producirse un error en la resolución de sobrecarga.  Se produce como un mensaje subordinado que indica por qué se ha eliminado un candidato de sobrecarga determinado.  El mensaje de error explica que el compilador no puede utilizar la inferencia de tipos para buscar tipos de datos para los parámetros de tipo.  
  
> [!NOTE]
>  Cuando la especificación de argumentos no es una opción \(por ejemplo, para operadores de consulta en expresiones de consulta\), el mensaje de error aparece sin la segunda frase.  
  
 El código siguiente muestra el error.  
  
```vb#  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 **Id. de error:** BC36647 y BC36644  
  
### Para corregir este error  
  
-   Es posible que pueda especificar un tipo de datos para los parámetros de tipo en lugar de basarse en la inferencia de tipos.  
  
## Vea también  
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Procedimientos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)