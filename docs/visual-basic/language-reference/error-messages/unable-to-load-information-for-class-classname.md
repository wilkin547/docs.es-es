---
description: "Más información sobre: BC30712: no se puede cargar la información de la clase ' <classname> '"
title: No se puede cargar información para la clase '<classname>'
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 5325afabfd267f15f0d0497be6ef03c8f5c828c0
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480536"
---
# <a name="bc30712-unable-to-load-information-for-class-classname"></a><span data-ttu-id="6d24e-103">BC30712: no se puede cargar la información de la clase ' \<classname> '</span><span class="sxs-lookup"><span data-stu-id="6d24e-103">BC30712: Unable to load information for class '\<classname>'</span></span>

<span data-ttu-id="6d24e-104">Se realizó una referencia a una clase que no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6d24e-104">A reference was made to a class that is not available.</span></span>

 <span data-ttu-id="6d24e-105">**Identificador de error:** BC30712</span><span class="sxs-lookup"><span data-stu-id="6d24e-105">**Error ID:** BC30712</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6d24e-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6d24e-106">To correct this error</span></span>

1. <span data-ttu-id="6d24e-107">Compruebe que la clase está definida y que ha escrito el nombre correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d24e-107">Verify that the class is defined and that you spelled the name correctly.</span></span>

2. <span data-ttu-id="6d24e-108">Intente obtener acceso a uno de los miembros declarados en el módulo.</span><span class="sxs-lookup"><span data-stu-id="6d24e-108">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="6d24e-109">En algunos casos, el entorno de depuración no encuentra los miembros porque los módulos donde se declaran no se han cargado todavía.</span><span class="sxs-lookup"><span data-stu-id="6d24e-109">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d24e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d24e-110">See also</span></span>

- [<span data-ttu-id="6d24e-111">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6d24e-111">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
