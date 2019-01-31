---
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: bc75b01532ffb112622d7f9bc837490c627883b3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270414"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>Propiedad predeterminada '\<nombrepropiedad1 >' entra en conflicto con la propiedad predeterminada '\<nombrepropiedad2 >' en '\<classname >', por lo que se debe declarar como 'Shadows'
Se declara una propiedad con el mismo nombre que una propiedad definida en la clase base. En esta situación, la propiedad de esta clase debe ocultar la propiedad de clase base.  
  
 Este mensaje es una advertencia. De forma predeterminada, se da por supuesto que es`Shadows` . Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40007  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Agregar el `Shadows` palabra clave para la declaración o cambie el nombre de la propiedad que se declara.  
  
## <a name="see-also"></a>Vea también
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
