---
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 290971a3173c59f08fbd279b6fffe3bcb618cb72
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160612"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>BC40007: la propiedad predeterminada ' \<propertyname1> ' entra en conflicto con la propiedad predeterminada ' \<propertyname2> ' en ' \<classname> ' y, por tanto, se debe declarar como ' Shadows '

Una propiedad se declara con el mismo nombre que una propiedad definida en la clase base. En esta situación, la propiedad de esta clase debe prevalecer en la propiedad de la clase base.

 Este mensaje es una advertencia. De forma predeterminada, se da por supuesto que es`Shadows` . Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC40007

## <a name="to-correct-this-error"></a>Para corregir este error

- Agregue la `Shadows` palabra clave a la declaración o cambie el nombre de la propiedad que se está declarando.

## <a name="see-also"></a>Vea también

- [Sombras](../modifiers/shadows.md)
- [Sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
