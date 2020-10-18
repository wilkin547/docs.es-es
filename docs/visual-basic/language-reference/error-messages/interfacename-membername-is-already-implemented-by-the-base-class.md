---
title: "\"<interfacename>.<membername>\" ya se ha implementado mediante la clase base \"<baseclassname>\". Se supone que <type> se implementa de nuevo"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 8137f6b1712b6a0752a991f5a3d598b5f958252c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162822"
---
# <a name="bc42015-interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="9f798-103">\<interfacename> \<membername> La clase base ' ' ya ha implementado BC42015: '. ' \<baseclassname> .</span><span class="sxs-lookup"><span data-stu-id="9f798-103">BC42015: '\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="9f798-104">Se supone que \<type> se implementa de nuevo</span><span class="sxs-lookup"><span data-stu-id="9f798-104">Re-implementation of \<type> assumed</span></span>

<span data-ttu-id="9f798-105">Una propiedad, un procedimiento o un evento en una clase derivada usa una `Implements` cláusula que especifica un miembro de interfaz que ya está implementado en la clase base.</span><span class="sxs-lookup"><span data-stu-id="9f798-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>

 <span data-ttu-id="9f798-106">Una clase derivada puede volver a implementar un miembro de interfaz implementado por su clase base.</span><span class="sxs-lookup"><span data-stu-id="9f798-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="9f798-107">Esto no es el mismo que reemplazar la implementación de la clase base.</span><span class="sxs-lookup"><span data-stu-id="9f798-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="9f798-108">Para obtener más información, consulte [Implements](../statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="9f798-108">For more information, see [Implements](../statements/implements-clause.md).</span></span>

 <span data-ttu-id="9f798-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="9f798-109">By default, this message is a warning.</span></span> <span data-ttu-id="9f798-110">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9f798-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="9f798-111">**Identificador de error:** BC42015</span><span class="sxs-lookup"><span data-stu-id="9f798-111">**Error ID:** BC42015</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9f798-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9f798-112">To correct this error</span></span>

- <span data-ttu-id="9f798-113">Si piensa volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="9f798-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="9f798-114">El código de la clase derivada tiene acceso al miembro reimplementado a menos que use la `MyBase` palabra clave para tener acceso a la implementación de la clase base.</span><span class="sxs-lookup"><span data-stu-id="9f798-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>

- <span data-ttu-id="9f798-115">Si no tiene pensado volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la declaración de propiedad, procedimiento o evento.</span><span class="sxs-lookup"><span data-stu-id="9f798-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f798-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f798-116">See also</span></span>

- [<span data-ttu-id="9f798-117">Interfaces</span><span class="sxs-lookup"><span data-stu-id="9f798-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
