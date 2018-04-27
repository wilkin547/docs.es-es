---
title: Tipo de &#39; &lt;typename&gt; &#39; no está definido
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7c3efbcabf1e40c7f550b5f54d16e697561cf82c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="40b67-102">Tipo de &#39; &lt;typename&gt; &#39; no está definido</span><span class="sxs-lookup"><span data-stu-id="40b67-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="40b67-103">La instrucción ha hecho referencia a un tipo que no se ha definido.</span><span class="sxs-lookup"><span data-stu-id="40b67-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="40b67-104">Puede definir un tipo en una instrucción de declaración como `Enum`, `Structure`, `Class`, o `Interface`.</span><span class="sxs-lookup"><span data-stu-id="40b67-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="40b67-105">**Id. de error:** BC30002</span><span class="sxs-lookup"><span data-stu-id="40b67-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="40b67-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="40b67-106">To correct this error</span></span>  
  
-   <span data-ttu-id="40b67-107">Asegúrese de que la definición de tipo y su referencia utilizan la misma ortografía.</span><span class="sxs-lookup"><span data-stu-id="40b67-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="40b67-108">Asegúrese de que la definición de tipo es accesible para la referencia.</span><span class="sxs-lookup"><span data-stu-id="40b67-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="40b67-109">Por ejemplo, si el tipo está en otro módulo y se ha declarado `Private`, mueva la definición de tipo al que hace referencia a módulo o declárelo `Public`.</span><span class="sxs-lookup"><span data-stu-id="40b67-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="40b67-110">Asegúrese de que el espacio de nombres del tipo no se vuelve a definir dentro de su proyecto.</span><span class="sxs-lookup"><span data-stu-id="40b67-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="40b67-111">Si es así, utilice el `Global` palabra clave para calificar totalmente el nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="40b67-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="40b67-112">Por ejemplo, si un proyecto que define un espacio de nombres denominado `System`, el <xref:System.Object?displayProperty=nameWithType> tipo no son accesibles a menos que esté completo con el `Global` palabra clave: `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="40b67-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="40b67-113">Si el tipo está definido, pero no se registra la biblioteca de objetos o la biblioteca de tipos en el que se define en Visual Basic, haga clic **Agregar referencia** en el **proyecto** menú y, a continuación, seleccione el objeto apropiado biblioteca o biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="40b67-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="40b67-114">Asegúrese de que el tipo está en un ensamblado que forma parte del perfil de .NET Framework de destino.</span><span class="sxs-lookup"><span data-stu-id="40b67-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="40b67-115">Para obtener más información, consulte [Solucionar problemas de versión de .NET Framework de destino](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="40b67-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b67-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="40b67-116">See Also</span></span>  
 [<span data-ttu-id="40b67-117">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40b67-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="40b67-118">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="40b67-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="40b67-119">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="40b67-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="40b67-120">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="40b67-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="40b67-121">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="40b67-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="40b67-122">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="40b67-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
