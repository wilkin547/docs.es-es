---
description: "Más información sobre: BC30685: ' <membername> ' es ambiguo en las interfaces heredadas ' <interfacename1> ' y '<interfacename2>"
title: "'<membername>' es ambiguo en las interfaces heredadas '<interfacename1>' y '<interfacename2>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: 8d114755c4456c7e846c2e9570481abfd5d13bbf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795838"
---
# <a name="bc30685-membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="6a846-103">BC30685: ' \<membername> ' es ambiguo en las interfaces heredadas ' \<interfacename1> ' y ' \<interfacename2> '</span><span class="sxs-lookup"><span data-stu-id="6a846-103">BC30685: '\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>

<span data-ttu-id="6a846-104">La interfaz hereda dos o más miembros con el mismo nombre de varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="6a846-104">The interface inherits two or more members with the same name from multiple interfaces.</span></span>

 <span data-ttu-id="6a846-105">**Identificador de error:** BC30685</span><span class="sxs-lookup"><span data-stu-id="6a846-105">**Error ID:** BC30685</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6a846-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6a846-106">To correct this error</span></span>

- <span data-ttu-id="6a846-107">Convierta el valor a la interfaz base que desea utilizar; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6a846-107">Cast the value to the base interface that you want to use; for example:</span></span>

    ```vb
    Interface Left
        Sub MySub()
    End Interface

    Interface Right
        Sub MySub()
    End Interface

    Interface LeftRight
        Inherits Left, Right
    End Interface

    Module test
        Sub Main()
            Dim x As LeftRight
            ' x.MySub()  'x is ambiguous.
            CType(x, Left).MySub() ' Cast to base type.
            CType(x, Right).MySub() ' Call the other base type.
        End Sub
    End Module
    ```

## <a name="see-also"></a><span data-ttu-id="6a846-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a846-108">See also</span></span>

- [<span data-ttu-id="6a846-109">Interfaces</span><span class="sxs-lookup"><span data-stu-id="6a846-109">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
