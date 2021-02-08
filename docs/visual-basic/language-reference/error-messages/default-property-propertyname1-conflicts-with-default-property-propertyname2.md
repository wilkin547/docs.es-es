---
description: "Más información sobre: BC40007: la propiedad predeterminada ' <propertyname1> ' entra en conflicto con la propiedad predeterminada ' <propertyname2> ' en ' <classname> ' y, por tanto, se debe declarar como ' Shadows '"
title: La propiedad predeterminada '<propertyname1>' está en conflicto con la propiedad predeterminada '<propertyname2>' en la base '<classname>' y, por tanto, se debe declarar como 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 8ec7e36da18bbf8dda35e1a521d64268d14b7b26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796644"
---
# <a name="bc40007-default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>BC40007: la propiedad predeterminada ' \<propertyname1> ' entra en conflicto con la propiedad predeterminada ' \<propertyname2> ' en ' \<classname> ' y, por tanto, se debe declarar como ' Shadows '

Una propiedad se declara con el mismo nombre que una propiedad definida en la clase base. En esta situación, la propiedad de esta clase debe prevalecer en la propiedad de la clase base.

 Este mensaje es una advertencia. De forma predeterminada, se da por supuesto que es`Shadows` . Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC40007

## <a name="to-correct-this-error"></a>Para corregir este error

- Agregue la `Shadows` palabra clave a la declaración o cambie el nombre de la propiedad que se está declarando.

## <a name="see-also"></a>Vea también

- [Shadows](../modifiers/shadows.md)
- [Sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
