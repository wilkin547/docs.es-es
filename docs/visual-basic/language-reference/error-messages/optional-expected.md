---
description: "Más información acerca de: se esperaba BC30202: ' Optional '"
title: Se esperaba 'Optional'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 543dbf6226d4d298d46764ee506b55e770c91604
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795552"
---
# <a name="bc30202-optional-expected"></a><span data-ttu-id="ff71f-103">BC30202: se esperaba ' Optional '</span><span class="sxs-lookup"><span data-stu-id="ff71f-103">BC30202: 'Optional' expected</span></span>

<span data-ttu-id="ff71f-104">Un argumento opcional en una declaración de procedimiento va seguido de un argumento necesario.</span><span class="sxs-lookup"><span data-stu-id="ff71f-104">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="ff71f-105">Cada argumento que siga a un argumento opcional también debe ser opcional.</span><span class="sxs-lookup"><span data-stu-id="ff71f-105">Every argument following an optional argument must also be optional.</span></span>

 <span data-ttu-id="ff71f-106">**Identificador de error:** BC30202</span><span class="sxs-lookup"><span data-stu-id="ff71f-106">**Error ID:** BC30202</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="ff71f-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ff71f-107">To correct this error</span></span>

- <span data-ttu-id="ff71f-108">Si el argumento está pensado para ser necesario, muévalo para que preceda al primer argumento opcional de la lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="ff71f-108">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>

- <span data-ttu-id="ff71f-109">Si el argumento está pensado para ser opcional, use la `Optional` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ff71f-109">If the argument is intended to be optional, use the `Optional` keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff71f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff71f-110">See also</span></span>

- [<span data-ttu-id="ff71f-111">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="ff71f-111">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
