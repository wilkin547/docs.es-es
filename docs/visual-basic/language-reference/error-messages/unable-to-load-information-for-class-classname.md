---
title: No se puede cargar información para la clase '<classname>'
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 05c3303db90a396479bc396c5c2395c3afbb59ae
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161613"
---
# <a name="bc30712-unable-to-load-information-for-class-classname"></a><span data-ttu-id="a7340-102">BC30712: no se puede cargar la información de la clase ' \<classname> '</span><span class="sxs-lookup"><span data-stu-id="a7340-102">BC30712: Unable to load information for class '\<classname>'</span></span>

<span data-ttu-id="a7340-103">Se realizó una referencia a una clase que no está disponible.</span><span class="sxs-lookup"><span data-stu-id="a7340-103">A reference was made to a class that is not available.</span></span>

 <span data-ttu-id="a7340-104">**Identificador de error:** BC30712</span><span class="sxs-lookup"><span data-stu-id="a7340-104">**Error ID:** BC30712</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a7340-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a7340-105">To correct this error</span></span>

1. <span data-ttu-id="a7340-106">Compruebe que la clase está definida y que ha escrito el nombre correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7340-106">Verify that the class is defined and that you spelled the name correctly.</span></span>

2. <span data-ttu-id="a7340-107">Intente obtener acceso a uno de los miembros declarados en el módulo.</span><span class="sxs-lookup"><span data-stu-id="a7340-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="a7340-108">En algunos casos, el entorno de depuración no encuentra los miembros porque los módulos donde se declaran no se han cargado todavía.</span><span class="sxs-lookup"><span data-stu-id="a7340-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7340-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7340-109">See also</span></span>

- [<span data-ttu-id="a7340-110">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a7340-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
