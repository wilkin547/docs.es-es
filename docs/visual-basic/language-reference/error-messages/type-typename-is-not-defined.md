---
title: No está definido el tipo '<typename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 195e749e29494d438dbd052e8e308250f4cce1ca
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161899"
---
# <a name="bc30002-type-typename-is-not-defined"></a><span data-ttu-id="0457d-102">BC30002: el tipo ' \<typename> ' no está definido</span><span class="sxs-lookup"><span data-stu-id="0457d-102">BC30002: Type '\<typename>' is not defined</span></span>

<span data-ttu-id="0457d-103">La instrucción ha hecho referencia a un tipo que no se ha definido.</span><span class="sxs-lookup"><span data-stu-id="0457d-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="0457d-104">Puede definir un tipo en una instrucción de declaración como `Enum` , `Structure` , `Class` o `Interface` .</span><span class="sxs-lookup"><span data-stu-id="0457d-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>

 <span data-ttu-id="0457d-105">**Identificador de error:** BC30002</span><span class="sxs-lookup"><span data-stu-id="0457d-105">**Error ID:** BC30002</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0457d-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0457d-106">To correct this error</span></span>

- <span data-ttu-id="0457d-107">Asegúrese de que la definición de tipo y su referencia usan la misma ortografía.</span><span class="sxs-lookup"><span data-stu-id="0457d-107">Ensure that the type definition and its reference both use the same spelling.</span></span>

- <span data-ttu-id="0457d-108">Asegúrese de que la definición de tipo es accesible para la referencia.</span><span class="sxs-lookup"><span data-stu-id="0457d-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="0457d-109">Por ejemplo, si el tipo está en otro módulo y se ha declarado `Private` , mueva la definición de tipo al módulo que hace la referencia o declárela `Public` .</span><span class="sxs-lookup"><span data-stu-id="0457d-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>

- <span data-ttu-id="0457d-110">Asegúrese de que el espacio de nombres del tipo no se ha redefinido en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0457d-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="0457d-111">Si es así, use la `Global` palabra clave para completar el nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="0457d-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="0457d-112">Por ejemplo, si un proyecto define un espacio de nombres denominado `System` , <xref:System.Object?displayProperty=nameWithType> no se puede tener acceso al tipo a menos que esté completo con la `Global` palabra clave: `Global.System.Object` .</span><span class="sxs-lookup"><span data-stu-id="0457d-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>

- <span data-ttu-id="0457d-113">Si se define el tipo, pero la biblioteca de objetos o la biblioteca de tipos en la que se define no está registrada en Visual Basic, haga clic en **Agregar referencia** en el menú **proyecto** y, a continuación, seleccione la biblioteca de objetos o la biblioteca de tipos adecuada.</span><span class="sxs-lookup"><span data-stu-id="0457d-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>

- <span data-ttu-id="0457d-114">Asegúrese de que el tipo está en un ensamblado que forma parte del perfil de .NET Framework de destino.</span><span class="sxs-lookup"><span data-stu-id="0457d-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="0457d-115">Para obtener más información, consulte [Solucionar problemas de versión de .NET Framework de destino](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="0457d-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>

## <a name="see-also"></a><span data-ttu-id="0457d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0457d-116">See also</span></span>

- [<span data-ttu-id="0457d-117">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0457d-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="0457d-118">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="0457d-118">Enum Statement</span></span>](../statements/enum-statement.md)
- [<span data-ttu-id="0457d-119">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="0457d-119">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="0457d-120">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="0457d-120">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="0457d-121">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="0457d-121">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="0457d-122">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="0457d-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
