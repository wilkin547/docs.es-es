---
title: Conforme a CLS no &lt;membername&gt; no se permite en una interfaz conforme a CLS
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 358abd338d3ce780c2f0aae7aa8efb53e57b477c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="5c684-102">Conforme a CLS no &lt;membername&gt; no se permite en una interfaz conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="5c684-102">Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="5c684-103">Una propiedad, procedimiento o evento de una interfaz se marca como `<CLSCompliant(True)>` cuando la propia interfaz está marcada como `<CLSCompliant(False)>` o no está marcada.</span><span class="sxs-lookup"><span data-stu-id="5c684-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="5c684-104">Para una interfaz ser compatible con la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), deben ser compatible con todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="5c684-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="5c684-105">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="5c684-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="5c684-106">No hay ningún valor predeterminado para este parámetro y debe proporcionar un valor.</span><span class="sxs-lookup"><span data-stu-id="5c684-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="5c684-107">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="5c684-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="5c684-108">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="5c684-108">By default, this message is a warning.</span></span> <span data-ttu-id="5c684-109">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5c684-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5c684-110">**Id. de error:** BC40033</span><span class="sxs-lookup"><span data-stu-id="5c684-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5c684-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5c684-111">To correct this error</span></span>  
  
-   <span data-ttu-id="5c684-112">Si requiere conformidad con CLS y tiene control sobre el código fuente de interfaz, marque la interfaz como `<CLSCompliant(True)>` si todos sus miembros son compatibles.</span><span class="sxs-lookup"><span data-stu-id="5c684-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="5c684-113">Si requiere conformidad con CLS y no tiene control sobre el código fuente de interfaz, o si no reúne los requisitos para ser compatible, defina a este miembro dentro de una interfaz diferente.</span><span class="sxs-lookup"><span data-stu-id="5c684-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="5c684-114">Si necesita que este miembro permanezca dentro de su interfaz actual, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="5c684-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c684-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c684-115">See Also</span></span>  
 [<span data-ttu-id="5c684-116">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5c684-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="5c684-117">\<PAVE sobre > escribir código conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="5c684-117">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
