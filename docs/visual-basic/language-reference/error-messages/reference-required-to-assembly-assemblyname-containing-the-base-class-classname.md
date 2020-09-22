---
title: Es necesaria una referencia al ensamblado '<assemblyname>' que contenga la clase base '<classname>'
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: 07c09d0dfcb374b974fbda9099c4e85d6d054753
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870907"
---
# <a name="reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a><span data-ttu-id="0777c-102">Es necesaria una referencia al ensamblado '\<assemblyname>' que contenga la clase base '\<classname>'</span><span class="sxs-lookup"><span data-stu-id="0777c-102">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'</span></span>

<span data-ttu-id="0777c-103">Es necesaria una referencia al ensamblado ' \<assemblyname> ' que contiene la clase base ' \<classname> '.</span><span class="sxs-lookup"><span data-stu-id="0777c-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="0777c-104">Agregue una al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0777c-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="0777c-105">La clase está definida en una biblioteca de vínculos dinámicos (DLL) o un ensamblado al que no se hace referencia directamente en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0777c-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="0777c-106">El compilador Visual Basic requiere una referencia para evitar la ambigüedad en caso de que la clase esté definida en más de una DLL o ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0777c-106">The Visual Basic compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="0777c-107">**Identificador de error:** BC30007</span><span class="sxs-lookup"><span data-stu-id="0777c-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0777c-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0777c-108">To correct this error</span></span>  
  
- <span data-ttu-id="0777c-109">Incluya el nombre de la DLL o el ensamblado no referenciados en las referencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0777c-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0777c-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0777c-110">See also</span></span>

- [<span data-ttu-id="0777c-111">Administrar referencias en un proyecto</span><span class="sxs-lookup"><span data-stu-id="0777c-111">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="0777c-112">Solucionar problemas de referencias rotas</span><span class="sxs-lookup"><span data-stu-id="0777c-112">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
