---
title: "&lt;proceduresignature1&gt; no es conforme a CLS porque sobrecarga &lt;proceduresignature2&gt; que difiere de él en la matriz de tipos de parámetro de matriz o el rango de los tipos de parámetro de matriz"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords: BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa9fca7f0590846f60577787aa476539a2c872a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a><span data-ttu-id="99c0c-102">&lt;proceduresignature1&gt; no es conforme a CLS porque sobrecarga &lt;proceduresignature2&gt; que difiere de él en la matriz de tipos de parámetro de matriz o el rango de los tipos de parámetro de matriz</span><span class="sxs-lookup"><span data-stu-id="99c0c-102">&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types</span></span>
<span data-ttu-id="99c0c-103">Un procedimiento o propiedad está marcada como `<CLSCompliant(True)>` cuando reemplaza otro procedimiento o propiedad y la única diferencia entre sus listas de parámetros es el nivel de anidamiento de una matriz escalonada o el rango de una matriz.</span><span class="sxs-lookup"><span data-stu-id="99c0c-103">A procedure or property is marked as `<CLSCompliant(True)>` when it overrides another procedure or property and the only difference between their parameter lists is the nesting level of a jagged array or the rank of an array.</span></span>  
  
 <span data-ttu-id="99c0c-104">En las declaraciones siguientes, la segunda y tercera declaraciones generan este error.</span><span class="sxs-lookup"><span data-stu-id="99c0c-104">In the following declarations, the second and third declarations generate this error.</span></span>  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 <span data-ttu-id="99c0c-105">La segunda declaración cambia el parámetro unidimensional original `arrayParam` a una matriz de matrices.</span><span class="sxs-lookup"><span data-stu-id="99c0c-105">The second declaration changes the original one-dimensional parameter `arrayParam` to an array of arrays.</span></span> <span data-ttu-id="99c0c-106">Los cambios en la terceros declaración `arrayParam` a una matriz bidimensional (rango 2).</span><span class="sxs-lookup"><span data-stu-id="99c0c-106">The third declaration changes `arrayParam` to a two-dimensional array (rank 2).</span></span> <span data-ttu-id="99c0c-107">Aunque Visual Basic permite sobrecargas para solamente se distinguen por uno de estos cambios, la sobrecarga de este tipo no es compatible con la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="99c0c-107">While Visual Basic allows overloads to differ only by one of these changes, such overloading is not compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span>  
  
 <span data-ttu-id="99c0c-108">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="99c0c-108">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="99c0c-109">No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.</span><span class="sxs-lookup"><span data-stu-id="99c0c-109">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="99c0c-110">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="99c0c-110">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="99c0c-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="99c0c-111">By default, this message is a warning.</span></span> <span data-ttu-id="99c0c-112">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="99c0c-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="99c0c-113">**Id. de error:** BC40035</span><span class="sxs-lookup"><span data-stu-id="99c0c-113">**Error ID:** BC40035</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="99c0c-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="99c0c-114">To correct this error</span></span>  
  
-   <span data-ttu-id="99c0c-115">Si necesita conformidad con CLS, defina sus sobrecargas para que coincidan entre sí de más formas que solo los cambios mencionados en esta página de ayuda.</span><span class="sxs-lookup"><span data-stu-id="99c0c-115">If you require CLS compliance, define your overloads to differ from each other in more ways than only the changes cited on this Help page.</span></span>  
  
-   <span data-ttu-id="99c0c-116">Si necesita que las sobrecargas difieren solo por los cambios mencionados en esta ayuda página, quite el <xref:System.CLSCompliantAttribute> de sus definiciones o se marcan como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="99c0c-116">If you require that the overloads differ only by the changes cited on this Help page, remove the <xref:System.CLSCompliantAttribute> from their definitions or mark them as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c0c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="99c0c-117">See Also</span></span>  
 [<span data-ttu-id="99c0c-118">\<PAVE sobre > escribir código conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="99c0c-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)  
 [<span data-ttu-id="99c0c-119">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="99c0c-119">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="99c0c-120">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="99c0c-120">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
