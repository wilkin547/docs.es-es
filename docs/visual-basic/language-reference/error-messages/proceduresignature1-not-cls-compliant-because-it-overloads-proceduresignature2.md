---
description: 'Más información acerca de: BC40035: <proceduresignature1> no es conforme a CLS porque sobrecarga <proceduresignature2> que solo difiere de él en la matriz de tipos de parámetro de matriz o en el rango de los tipos de parámetro de matriz'
title: <proceduresignature1> no es compatible con CLS porque sobrecarga a <proceduresignature2>, que difiere de ella solo en la matriz de tipos de parámetro de matriz o el rango de los tipos de parámetro de matriz
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 056683033a4eacdc6ad783f5056b639e849e3507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795396"
---
# <a name="bc40035-proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>BC40035: \<proceduresignature1> no es conforme a CLS porque sobrecarga \<proceduresignature2> que difiere de él solo en la matriz de tipos de parámetro de matriz o en el rango de los tipos de parámetro de matriz

Un procedimiento o una propiedad se marca como `<CLSCompliant(True)>` cuando invalida otro procedimiento o propiedad y la única diferencia entre sus listas de parámetros es el nivel de anidamiento de una matriz escalonada o el rango de una matriz.

 En las declaraciones siguientes, las declaraciones segunda y tercera generan este error:

 `Overloads Sub ProcessArray(arrayParam() As Integer)`

 `Overloads Sub ProcessArray(arrayParam()() As Integer)`

 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`

 La segunda declaración cambia el parámetro unidimensional original `arrayParam` a una matriz de matrices. La tercera declaración cambia `arrayParam` a una matriz bidimensional (rango 2). Aunque Visual Basic permite que las sobrecargas solo difieran en uno de estos cambios, tal sobrecarga no es compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS).

 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad. No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.

 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.

 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC40035

## <a name="to-correct-this-error"></a>Para corregir este error

- Si requiere la conformidad con CLS, defina las sobrecargas para que difieran entre sí de forma más distinta que solo los cambios citados en esta página de ayuda.
- Si necesita que las sobrecargas solo difieran en los cambios citados en esta página de ayuda, quite <xref:System.CLSCompliantAttribute> de sus definiciones o márquela como `<CLSCompliant(False)>` .

## <a name="see-also"></a>Vea también

- [Sobrecarga de procedimientos](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Sobrecargas](../modifiers/overloads.md)
