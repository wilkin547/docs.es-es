---
title: "'<interfacename>. <membername>'ya está implementado por la clase base'<baseclassname>'. Reimplementación de <type> supone"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 5943eff5fa7e68da9905e3e589eea264c06943c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593316"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="879aa-103">'\<nombreDeInterfaz >. \<membername >' ya está implementado por la clase base\<nombredeclasebase >'.</span><span class="sxs-lookup"><span data-stu-id="879aa-103">'\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="879aa-104">Reimplementación de \<tipo > supone</span><span class="sxs-lookup"><span data-stu-id="879aa-104">Re-implementation of \<type> assumed</span></span>
<span data-ttu-id="879aa-105">Una propiedad, procedimiento o evento en una clase derivada utiliza una `Implements` cláusula que especifica un miembro de interfaz que ya está implementado en la clase base.</span><span class="sxs-lookup"><span data-stu-id="879aa-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="879aa-106">Una clase derivada puede volver a implementar un miembro de interfaz implementado por su clase base.</span><span class="sxs-lookup"><span data-stu-id="879aa-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="879aa-107">Esto no es el mismo que reemplazar la implementación de la clase base.</span><span class="sxs-lookup"><span data-stu-id="879aa-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="879aa-108">Para obtener más información, consulte [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="879aa-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="879aa-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="879aa-109">By default, this message is a warning.</span></span> <span data-ttu-id="879aa-110">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="879aa-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="879aa-111">**Identificador de error:** BC42015</span><span class="sxs-lookup"><span data-stu-id="879aa-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="879aa-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="879aa-112">To correct this error</span></span>  
  
- <span data-ttu-id="879aa-113">Si piensa volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="879aa-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="879aa-114">Código de la clase derivada tiene acceso al miembro nuevamente implementado a menos que use el `MyBase` palabra clave para acceder a la implementación de la clase base.</span><span class="sxs-lookup"><span data-stu-id="879aa-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
- <span data-ttu-id="879aa-115">Si no tiene pensado volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la declaración de propiedad, procedimiento o evento.</span><span class="sxs-lookup"><span data-stu-id="879aa-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879aa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="879aa-116">See also</span></span>

- [<span data-ttu-id="879aa-117">Interfaces</span><span class="sxs-lookup"><span data-stu-id="879aa-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
