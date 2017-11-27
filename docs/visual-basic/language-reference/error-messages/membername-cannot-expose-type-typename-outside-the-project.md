---
title: "&#39; &lt;membername&gt;&#39; no puede exponer el tipo &#39;&lt; TypeName&gt;&#39; fuera del proyecto a través de &lt;containertype&gt; &#39;&lt; containertypename&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords: BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd64c815286a5ffec111bcf1f68674a8e3558403
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39; &lt;membername&gt;&#39; no puede exponer el tipo &#39;&lt; TypeName&gt;&#39; fuera del proyecto a través de &lt;containertype&gt; &#39;&lt; containertypename&gt;&#39;
Una variable, parámetro de procedimiento o valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.  
  
 La estructura de código siguiente muestra una situación que genera este error.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo que se declara `Protected`, `Friend`, `Protected Friend`, o `Private` está diseñado para tener acceso limitado fuera de su contexto de declaración. Lo usa como los datos de tipo de una variable con acceso menos restringido iría contra este propósito. En el código anterior de esqueleto, `exposedVar` es `Public` y expondría `privateClass` al código que no debe tener acceso a él.  
  
 **Id. de error:** BC30909  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar el nivel de acceso de la variable, el parámetro de procedimiento o la función devuelve para que sea al menos tan restrictiva como el nivel de acceso de su tipo de datos.  
  
## <a name="see-also"></a>Vea también  
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
