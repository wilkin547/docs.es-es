---
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: ab45278b2e1199282e3066c34828b9bda716e162
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813176"
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
