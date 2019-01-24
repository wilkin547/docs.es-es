---
title: Propiedad predeterminada &#39; &lt;nombrepropiedad1&gt; &#39; entra en conflicto con la propiedad predeterminada &#39; &lt;propertyname2&gt; &#39; en &#39; &lt;classname&gt; &#39;, por lo que se debe declarar como &#39;sombras&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 3099467fa3c5a162c13c9235fb8d55375953ba3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521431"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Propiedad predeterminada &#39; &lt;nombrepropiedad1&gt; &#39; entra en conflicto con la propiedad predeterminada &#39; &lt;propertyname2&gt; &#39; en &#39; &lt;classname&gt; &#39;, por lo que se debe declarar como &#39;sombras&#39;
Se declara una propiedad con el mismo nombre que una propiedad definida en la clase base. En esta situación, la propiedad de esta clase debe ocultar la propiedad de clase base.  
  
 Este mensaje es una advertencia. De forma predeterminada, se da por supuesto que es`Shadows` . Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40007  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Agregar el `Shadows` palabra clave para la declaración o cambie el nombre de la propiedad que se declara.  
  
## <a name="see-also"></a>Vea también
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
