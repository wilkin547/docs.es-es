---
title: "'<membername>' es ambiguo en las interfaces heredadas '<interfacename1>' y '<interfacename2>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: f666bf380f8b94c50c2bc5fd865b37d96e92991f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162445"
---
# <a name="bc30685-membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="65c76-102">BC30685: ' \<membername> ' es ambiguo en las interfaces heredadas ' \<interfacename1> ' y ' \<interfacename2> '</span><span class="sxs-lookup"><span data-stu-id="65c76-102">BC30685: '\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>

<span data-ttu-id="65c76-103">La interfaz hereda dos o más miembros con el mismo nombre de varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="65c76-103">The interface inherits two or more members with the same name from multiple interfaces.</span></span>

 <span data-ttu-id="65c76-104">**Identificador de error:** BC30685</span><span class="sxs-lookup"><span data-stu-id="65c76-104">**Error ID:** BC30685</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="65c76-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="65c76-105">To correct this error</span></span>

- <span data-ttu-id="65c76-106">Convierta el valor a la interfaz base que desea utilizar; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="65c76-106">Cast the value to the base interface that you want to use; for example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="65c76-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="65c76-107">See also</span></span>

- [<span data-ttu-id="65c76-108">Interfaces</span><span class="sxs-lookup"><span data-stu-id="65c76-108">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
