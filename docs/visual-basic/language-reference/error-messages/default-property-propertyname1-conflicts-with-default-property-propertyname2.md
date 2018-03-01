---
title: "Propiedad predeterminada &#39; &lt;nombrepropiedad1&gt;&#39; está en conflicto con la propiedad predeterminada &#39;&lt; propertyName2&gt;&#39; en &#39;&lt; ClassName&gt;&#39; por lo que se debe declarar como &#39; Las sombras &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af92c06f6d07b6ea64a05b9043547a46e3679111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Propiedad predeterminada &#39; &lt;nombrepropiedad1&gt;&#39; está en conflicto con la propiedad predeterminada &#39;&lt; propertyName2&gt;&#39; en &#39;&lt; ClassName&gt;&#39; por lo que se debe declarar como &#39; Las sombras &#39;
Se declara una propiedad con el mismo nombre que una propiedad definida en la clase base. En esta situación, la propiedad de esta clase debe ocultar la propiedad de clase base.  
  
 Este mensaje es una advertencia. De forma predeterminada, se da por supuesto que es`Shadows` . Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC40007  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Agregar el `Shadows` palabra clave para la declaración o cambie el nombre de la propiedad que se declara.  
  
## <a name="see-also"></a>Vea también  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
