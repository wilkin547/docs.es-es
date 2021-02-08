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
# <a name="bc40035-proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="9e232-103">BC40035: \<proceduresignature1> no es conforme a CLS porque sobrecarga \<proceduresignature2> que difiere de él solo en la matriz de tipos de parámetro de matriz o en el rango de los tipos de parámetro de matriz</span><span class="sxs-lookup"><span data-stu-id="9e232-103">BC40035: \<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>

<span data-ttu-id="9e232-104">Un procedimiento o una propiedad se marca como `<CLSCompliant(True)>` cuando invalida otro procedimiento o propiedad y la única diferencia entre sus listas de parámetros es el nivel de anidamiento de una matriz escalonada o el rango de una matriz.</span><span class="sxs-lookup"><span data-stu-id="9e232-104">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>

 <span data-ttu-id="9e232-105">En las declaraciones siguientes, las declaraciones segunda y tercera generan este error:</span><span class="sxs-lookup"><span data-stu-id="9e232-105">In the following declarations, the second and third declarations generate this error:</span></span>

 `Overloads Sub ProcessArray(arrayParam() As Integer)`

 `Overloads Sub ProcessArray(arrayParam()() As Integer)`

 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`

 <span data-ttu-id="9e232-106">La segunda declaración cambia el parámetro unidimensional original `arrayParam` a una matriz de matrices.</span><span class="sxs-lookup"><span data-stu-id="9e232-106">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="9e232-107">La tercera declaración cambia `arrayParam` a una matriz bidimensional (rango 2).</span><span class="sxs-lookup"><span data-stu-id="9e232-107">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="9e232-108">Aunque Visual Basic permite que las sobrecargas solo difieran en uno de estos cambios, tal sobrecarga no es compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="9e232-108">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>

 <span data-ttu-id="9e232-109">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="9e232-109">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="9e232-110">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="9e232-110">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="9e232-111">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="9e232-111">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="9e232-112">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9e232-112">By default, this message is a warning.</span></span> <span data-ttu-id="9e232-113">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9e232-113">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="9e232-114">**Identificador de error:** BC40035</span><span class="sxs-lookup"><span data-stu-id="9e232-114">**Error ID:** BC40035</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9e232-115">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9e232-115">To correct this error</span></span>

- <span data-ttu-id="9e232-116">Si requiere la conformidad con CLS, defina las sobrecargas para que difieran entre sí de forma más distinta que solo los cambios citados en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="9e232-116">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>
- <span data-ttu-id="9e232-117">Si necesita que las sobrecargas solo difieran en los cambios citados en esta página de ayuda, quite <xref:System.CLSCompliantAttribute> de sus definiciones o márquela como `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="9e232-117">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e232-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e232-118">See also</span></span>

- [<span data-ttu-id="9e232-119">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="9e232-119">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="9e232-120">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="9e232-120">Overloads</span></span>](../modifiers/overloads.md)
