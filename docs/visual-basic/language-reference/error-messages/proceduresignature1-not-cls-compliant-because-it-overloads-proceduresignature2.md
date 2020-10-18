---
title: <proceduresignature1> no es compatible con CLS porque sobrecarga a <proceduresignature2>, que difiere de ella solo en la matriz de tipos de parámetro de matriz o el rango de los tipos de parámetro de matriz
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 5376f0513b1180da511a508cf8e0e754e8938384
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159799"
---
# <a name="bc40035-proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="11f1c-102">BC40035: \<proceduresignature1> no es conforme a CLS porque sobrecarga \<proceduresignature2> que difiere de él solo en la matriz de tipos de parámetro de matriz o en el rango de los tipos de parámetro de matriz</span><span class="sxs-lookup"><span data-stu-id="11f1c-102">BC40035: \<proceduresignature1> is not CLS-compliant because it overloads \<proceduresignature2> which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>

<span data-ttu-id="11f1c-103">Un procedimiento o una propiedad se marca como `<CLSCompliant(True)>` cuando invalida otro procedimiento o propiedad y la única diferencia entre sus listas de parámetros es el nivel de anidamiento de una matriz escalonada o el rango de una matriz.</span><span class="sxs-lookup"><span data-stu-id="11f1c-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>

 <span data-ttu-id="11f1c-104">En las declaraciones siguientes, las declaraciones segunda y tercera generan este error:</span><span class="sxs-lookup"><span data-stu-id="11f1c-104">In the following declarations, the second and third declarations generate this error:</span></span>

 `Overloads Sub ProcessArray(arrayParam() As Integer)`

 `Overloads Sub ProcessArray(arrayParam()() As Integer)`

 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`

 <span data-ttu-id="11f1c-105">La segunda declaración cambia el parámetro unidimensional original `arrayParam` a una matriz de matrices.</span><span class="sxs-lookup"><span data-stu-id="11f1c-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="11f1c-106">La tercera declaración cambia `arrayParam` a una matriz bidimensional (rango 2).</span><span class="sxs-lookup"><span data-stu-id="11f1c-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="11f1c-107">Aunque Visual Basic permite que las sobrecargas solo difieran en uno de estos cambios, tal sobrecarga no es compatible con la [independencia del lenguaje y los componentes de Language-Independent](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="11f1c-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>

 <span data-ttu-id="11f1c-108">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="11f1c-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="11f1c-109">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="11f1c-109">There is no default for this parameter, and you must supply a value.</span></span>

 <span data-ttu-id="11f1c-110">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="11f1c-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>

 <span data-ttu-id="11f1c-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="11f1c-111">By default, this message is a warning.</span></span> <span data-ttu-id="11f1c-112">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="11f1c-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="11f1c-113">**Identificador de error:** BC40035</span><span class="sxs-lookup"><span data-stu-id="11f1c-113">**Error ID:** BC40035</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="11f1c-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="11f1c-114">To correct this error</span></span>

- <span data-ttu-id="11f1c-115">Si requiere la conformidad con CLS, defina las sobrecargas para que difieran entre sí de forma más distinta que solo los cambios citados en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="11f1c-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>
- <span data-ttu-id="11f1c-116">Si necesita que las sobrecargas solo difieran en los cambios citados en esta página de ayuda, quite <xref:System.CLSCompliantAttribute> de sus definiciones o márquela como `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="11f1c-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="11f1c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="11f1c-117">See also</span></span>

- [<span data-ttu-id="11f1c-118">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="11f1c-118">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="11f1c-119">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="11f1c-119">Overloads</span></span>](../modifiers/overloads.md)
