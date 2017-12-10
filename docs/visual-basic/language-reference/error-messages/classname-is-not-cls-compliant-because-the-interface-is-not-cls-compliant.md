---
title: '&#39; &lt;classname&gt;&#39; no es conforme a CLS porque la interfaz &#39;&lt; InterfaceName&gt;&#39; se implementa no es compatible con CLS'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords: BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60c41332d3a5d93b05df906eefdeeb0d1b67e638
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2017
---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a><span data-ttu-id="6fd19-102">&#39; &lt;classname&gt;&#39; no es conforme a CLS porque la interfaz &#39;&lt; InterfaceName&gt;&#39; se implementa no es compatible con CLS</span><span class="sxs-lookup"><span data-stu-id="6fd19-102">&#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant</span></span>
<span data-ttu-id="6fd19-103">Una clase o interfaz se marca como `<CLSCompliant(True)>` cuando se deriva (o lo implementa) de un tipo marcado como `<CLSCompliant(False)>` o que no está marcado.</span><span class="sxs-lookup"><span data-stu-id="6fd19-103">A class or interface is marked as `<CLSCompliant(True)>` when it derives from or implements a type that is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="6fd19-104">Para una clase o interfaz sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), su jerarquía de herencia completa debe ser compatible.</span><span class="sxs-lookup"><span data-stu-id="6fd19-104">For a class or interface to be compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), its entire inheritance hierarchy must be compliant.</span></span> <span data-ttu-id="6fd19-105">Esto significa que cada tipo del que hereda, directa o indirectamente, debe ser compatible.</span><span class="sxs-lookup"><span data-stu-id="6fd19-105">That means every type from which it inherits, directly or indirectly, must be compliant.</span></span> <span data-ttu-id="6fd19-106">De forma similar, si una clase implementa una o varias interfaces, todas deben conformes a lo largo de su jerarquía de herencia.</span><span class="sxs-lookup"><span data-stu-id="6fd19-106">Similarly, if a class implements one or more interfaces, they must all be compliant throughout their inheritance hierarchies.</span></span>  
  
 <span data-ttu-id="6fd19-107">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="6fd19-107">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="6fd19-108">No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.</span><span class="sxs-lookup"><span data-stu-id="6fd19-108">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="6fd19-109">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="6fd19-109">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="6fd19-110">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="6fd19-110">By default, this message is a warning.</span></span> <span data-ttu-id="6fd19-111">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6fd19-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="6fd19-112">**Id. de error:** BC40029</span><span class="sxs-lookup"><span data-stu-id="6fd19-112">**Error ID:** BC40029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6fd19-113">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6fd19-113">To correct this error</span></span>  
  
-   <span data-ttu-id="6fd19-114">Si necesita compatibilidad con CLS, defina este tipo dentro de una jerarquía de herencia diferente para el esquema de implementación.</span><span class="sxs-lookup"><span data-stu-id="6fd19-114">If you require CLS compliance, define this type within a different inheritance hierarchy or implementation scheme.</span></span>  
  
-   <span data-ttu-id="6fd19-115">Si requiere que este tipo permanezca dentro de su esquema de implementación o de la jerarquía de herencia actuales, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="6fd19-115">If you require that this type remain within its current inheritance hierarchy or implementation scheme, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd19-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fd19-116">See Also</span></span>  
 [<span data-ttu-id="6fd19-117">\<PAVE sobre > escribir código conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="6fd19-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
