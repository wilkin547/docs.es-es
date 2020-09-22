---
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b857a9ae7875a156179602cbe77558333d07b7b9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874506"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>La propiedad predeterminada '\<propertyname1>' está en conflicto con la propiedad predeterminada '\<propertyname2>' en la base '\<classname>' y, por tanto, se debe declarar como 'Shadows'

Una propiedad se declara con el mismo nombre que una propiedad definida en la clase base. En esta situación, la propiedad de esta clase debe prevalecer en la propiedad de la clase base.  
  
 Este mensaje es una advertencia. De forma predeterminada, se da por supuesto que es`Shadows` . Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40007  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Agregue la `Shadows` palabra clave a la declaración o cambie el nombre de la propiedad que se está declarando.  
  
## <a name="see-also"></a>Consulte también

- [Shadows](../modifiers/shadows.md)
- [Sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
