---
title: No se puede hacer referencia a '<name>' porque es miembro del campo de tipo de valor '<name>' de la clase '<classname>' que tiene 'System.MarshalByRefObject' como clase base
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: aac190119ced74496c4dd012d200fca6d895ff28
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826774"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a><span data-ttu-id="eb167-102">No se puede hacer referencia a '\<nombre >' porque es un miembro del campo de tipo de valor '\<nombre >' de la clase\<classname >' que tiene 'System.MarshalByRefObject' como clase base</span><span class="sxs-lookup"><span data-stu-id="eb167-102">Cannot refer to '\<name>' because it is a member of the value-typed field '\<name>' of class '\<classname>' which has 'System.MarshalByRefObject' as a base class</span></span>
<span data-ttu-id="eb167-103">La `System.MarshalByRefObject` clase permite que las aplicaciones que admiten el acceso remoto a los objetos entre límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="eb167-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="eb167-104">Tipos deben heredar de la `MarshalByRejectObject` clase cuando el tipo se usa en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="eb167-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="eb167-105">No se debe copiar el estado del objeto porque los miembros del objeto no se puede usar fuera del dominio de aplicación en el que se crearon.</span><span class="sxs-lookup"><span data-stu-id="eb167-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="eb167-106">**Identificador de error:** BC30310</span><span class="sxs-lookup"><span data-stu-id="eb167-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eb167-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="eb167-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="eb167-108">Compruebe la referencia para asegurarse de que el miembro que se hace referencia es válido.</span><span class="sxs-lookup"><span data-stu-id="eb167-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="eb167-109">Califique explícitamente el miembro con el `Me` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="eb167-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb167-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb167-110">See also</span></span>

- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="eb167-111">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="eb167-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
