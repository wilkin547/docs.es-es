---
title: No está definido el tipo '<typename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 1f66b86a61fb0344a449bf0aa46b7655813c7c30
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664252"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="271c8-102">Tipo de '\<typename >' no está definido</span><span class="sxs-lookup"><span data-stu-id="271c8-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="271c8-103">La instrucción hace referencia a un tipo que no se ha definido.</span><span class="sxs-lookup"><span data-stu-id="271c8-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="271c8-104">Puede definir un tipo en una instrucción de declaración como `Enum`, `Structure`, `Class`, o `Interface`.</span><span class="sxs-lookup"><span data-stu-id="271c8-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="271c8-105">**Identificador de error:** BC30002</span><span class="sxs-lookup"><span data-stu-id="271c8-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="271c8-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="271c8-106">To correct this error</span></span>  
  
- <span data-ttu-id="271c8-107">Asegúrese de que la definición de tipo y su referencia usan la misma ortografía.</span><span class="sxs-lookup"><span data-stu-id="271c8-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="271c8-108">Asegúrese de que la definición de tipo es accesible para la referencia.</span><span class="sxs-lookup"><span data-stu-id="271c8-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="271c8-109">Por ejemplo, si el tipo está en otro módulo y se ha declarado `Private`, mueva la definición de tipo al que hace referencia a módulo o declárelo `Public`.</span><span class="sxs-lookup"><span data-stu-id="271c8-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="271c8-110">Asegúrese de que el espacio de nombres del tipo no se ha redefinido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="271c8-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="271c8-111">Si es así, utilice el `Global` palabra clave para el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="271c8-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="271c8-112">Por ejemplo, si un proyecto define un espacio de nombres denominado `System`, <xref:System.Object?displayProperty=nameWithType> tipo no se puede acceder a menos que se completa con el `Global` palabra clave: `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="271c8-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="271c8-113">Si el tipo está definido, pero no se registra la biblioteca de objetos o la biblioteca de tipos en el que se define en Visual Basic, haga clic **Agregar referencia** en el **proyecto** menú y, a continuación, seleccione el objeto adecuado biblioteca o biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="271c8-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="271c8-114">Asegúrese de que el tipo está en un ensamblado que es parte del perfil de .NET Framework de destino.</span><span class="sxs-lookup"><span data-stu-id="271c8-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="271c8-115">Para obtener más información, consulte [Solucionar problemas de versión de .NET Framework de destino](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="271c8-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="271c8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="271c8-116">See also</span></span>

- [<span data-ttu-id="271c8-117">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="271c8-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="271c8-118">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="271c8-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="271c8-119">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="271c8-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="271c8-120">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="271c8-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="271c8-121">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="271c8-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="271c8-122">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="271c8-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
