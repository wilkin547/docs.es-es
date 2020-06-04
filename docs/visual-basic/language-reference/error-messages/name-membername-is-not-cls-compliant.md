---
title: El nombre <membername> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: 45c9332237dffc7311daeedaf36035d9e9958415
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397186"
---
# <a name="name-membername-is-not-cls-compliant"></a><span data-ttu-id="2c499-102">El nombre \<membername> no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="2c499-102">Name \<membername> is not CLS-compliant</span></span>
<span data-ttu-id="2c499-103">Un ensamblado se marca como `<CLSCompliant(True)>` pero expone un miembro con un nombre que comienza con un carácter de subrayado ( `_` ).</span><span class="sxs-lookup"><span data-stu-id="2c499-103">An assembly is marked as `<CLSCompliant(True)>` but exposes a member with a name that begins with an underscore (`_`).</span></span>  
  
 <span data-ttu-id="2c499-104">Un elemento de programación puede contener uno o más guiones bajos, pero para que sea compatible con la [independencia del lenguaje y los componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), no debe comenzar con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="2c499-104">A programming element can contain one or more underscores, but to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must not begin with an underscore.</span></span> <span data-ttu-id="2c499-105">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="2c499-105">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 <span data-ttu-id="2c499-106">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="2c499-106">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="2c499-107">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="2c499-107">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="2c499-108">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="2c499-108">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="2c499-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="2c499-109">By default, this message is a warning.</span></span> <span data-ttu-id="2c499-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2c499-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2c499-111">**Identificador de error:** BC40031</span><span class="sxs-lookup"><span data-stu-id="2c499-111">**Error ID:** BC40031</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2c499-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2c499-112">To correct this error</span></span>  
  
- <span data-ttu-id="2c499-113">Si tiene control sobre el código fuente, cambie el nombre del miembro para que no comience por un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="2c499-113">If you have control over the source code, change the member name so that it does not begin with an underscore.</span></span>  
  
- <span data-ttu-id="2c499-114">Si necesita que el nombre de miembro permanezca inalterado, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>` .</span><span class="sxs-lookup"><span data-stu-id="2c499-114">If you require that the member name remain unchanged, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span> <span data-ttu-id="2c499-115">Todavía puede marcar el ensamblado como `<CLSCompliant(True)>` .</span><span class="sxs-lookup"><span data-stu-id="2c499-115">You can still mark the assembly as `<CLSCompliant(True)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c499-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c499-116">See also</span></span>

- [<span data-ttu-id="2c499-117">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="2c499-117">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="2c499-118">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c499-118">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
