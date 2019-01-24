---
title: '&#39;&lt;MemberName&gt; &#39; no se puede exponer el tipo &#39; &lt;typename&gt; &#39; fuera del proyecto mediante &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 39d316aca5ec306de4b1e43e2eb2d1495f5525d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672349"
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39;&lt;MemberName&gt; &#39; no se puede exponer el tipo &#39; &lt;typename&gt; &#39; fuera del proyecto mediante &lt;containertype&gt; &#39; &lt;containertypename&gt;&#39;
Una variable, parámetro de procedimiento o valor devuelto de función se expone fuera de su contenedor, pero se declara como un tipo que no se debe exponer fuera del contenedor.  
  
 La estructura de código siguiente muestra una situación que genera este error.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un tipo que se declara `Protected`, `Friend`, `Protected Friend`, o `Private` está diseñado para tener acceso limitado fuera de su contexto de declaración. Lo utilizan como los datos de tipo de una variable con acceso menos restringido iría con este fin. En el código anterior de esqueleto, `exposedVar` es `Public` y expondría `privateClass` al código que no debería tener acceso a él.  
  
 **Identificador de error:** BC30909  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Cambiar el nivel de acceso de la variable, parámetro de procedimiento o función que se devuelven para que sea al menos tan restrictiva como el nivel de acceso de su tipo de datos.  
  
## <a name="see-also"></a>Vea también
- [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
