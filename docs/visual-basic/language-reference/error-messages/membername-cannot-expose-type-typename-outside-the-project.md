---
title: "&#39;&lt;nombre de miembro&gt;&#39; no puede exponer el tipo &#39;&lt;nombre de tipo&gt;&#39; fuera del proyecto mediante &lt;tipo de contenedor&gt; &#39;&lt;nombre de tipo de contenedor&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30909"
  - "vbc30909"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30909"
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# &#39;&lt;nombre de miembro&gt;&#39; no puede exponer el tipo &#39;&lt;nombre de tipo&gt;&#39; fuera del proyecto mediante &lt;tipo de contenedor&gt; &#39;&lt;nombre de tipo de contenedor&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El valor devuelto por una variable, parámetro de procedimiento o función se expone fuera de su contenedor, pero se ha declarado como un tipo que no se debe exponer fuera del contenedor.  
  
 En el código estructural siguiente se muestra una situación que genera este error.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo que se declara como `Protected`, `Friend`, `Protected Friend` o `Private` está pensado para tener acceso limitado fuera de su contexto de declaración.  Al utilizarlo como el tipo de datos de una variable con acceso menos restringido, se incumpliría este propósito.  En el código estructural anterior, `exposedVar` es `Public` y expondría `privateClass` a código que no debería tener acceso a esa variable.  
  
 **Identificador de error:** BC30909  
  
### Para corregir este error  
  
-   Cambie el nivel de acceso del valor devuelto por la variable, parámetro de procedimiento o función para que sea, al menos, tan restrictivo como el nivel de acceso del tipo de datos correspondiente.  
  
## Vea también  
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)