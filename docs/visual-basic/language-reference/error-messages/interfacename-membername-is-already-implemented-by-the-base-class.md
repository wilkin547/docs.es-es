---
description: "Más información sobre: BC42015: ' <interfacename> . <membername> ' ya está implementado por la clase base ' <baseclassname> '. Se supone que <type> se implementa de nuevo"
title: "\"<interfacename>.<membername>\" ya se ha implementado mediante la clase base \"<baseclassname>\". Se supone que <type> se implementa de nuevo"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 7e9cce6250d21dfc4255d9971eea407b3a60e96a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796033"
---
# <a name="bc42015-interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="56f55-105">\<interfacename> \<membername> La clase base ' ' ya ha implementado BC42015: '. ' \<baseclassname> .</span><span class="sxs-lookup"><span data-stu-id="56f55-105">BC42015: '\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="56f55-106">Se supone que \<type> se implementa de nuevo</span><span class="sxs-lookup"><span data-stu-id="56f55-106">Re-implementation of \<type> assumed</span></span>

<span data-ttu-id="56f55-107">Una propiedad, un procedimiento o un evento en una clase derivada usa una `Implements` cláusula que especifica un miembro de interfaz que ya está implementado en la clase base.</span><span class="sxs-lookup"><span data-stu-id="56f55-107">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>

 <span data-ttu-id="56f55-108">Una clase derivada puede volver a implementar un miembro de interfaz implementado por su clase base.</span><span class="sxs-lookup"><span data-stu-id="56f55-108">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="56f55-109">Esto no es el mismo que reemplazar la implementación de la clase base.</span><span class="sxs-lookup"><span data-stu-id="56f55-109">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="56f55-110">Para obtener más información, consulte [Implements](../statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="56f55-110">For more information, see [Implements](../statements/implements-clause.md).</span></span>

 <span data-ttu-id="56f55-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="56f55-111">By default, this message is a warning.</span></span> <span data-ttu-id="56f55-112">Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="56f55-112">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="56f55-113">**Identificador de error:** BC42015</span><span class="sxs-lookup"><span data-stu-id="56f55-113">**Error ID:** BC42015</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="56f55-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="56f55-114">To correct this error</span></span>

- <span data-ttu-id="56f55-115">Si piensa volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="56f55-115">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="56f55-116">El código de la clase derivada tiene acceso al miembro reimplementado a menos que use la `MyBase` palabra clave para tener acceso a la implementación de la clase base.</span><span class="sxs-lookup"><span data-stu-id="56f55-116">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>

- <span data-ttu-id="56f55-117">Si no tiene pensado volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la declaración de propiedad, procedimiento o evento.</span><span class="sxs-lookup"><span data-stu-id="56f55-117">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="56f55-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="56f55-118">See also</span></span>

- [<span data-ttu-id="56f55-119">Interfaces</span><span class="sxs-lookup"><span data-stu-id="56f55-119">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
