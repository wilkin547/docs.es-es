---
title: Diseño de campos
ms.date: 10/22/2008
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 4329ca9e74fa02411bd39755a432fc7d4858597d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706702"
---
# <a name="field-design"></a><span data-ttu-id="fc84f-102">Diseño de campos</span><span class="sxs-lookup"><span data-stu-id="fc84f-102">Field Design</span></span>

<span data-ttu-id="fc84f-103">El principio de encapsulación es una de las nociones más importantes del diseño orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="fc84f-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="fc84f-104">Este principio indica que los datos almacenados dentro de un objeto solo deben ser accesibles para ese objeto.</span><span class="sxs-lookup"><span data-stu-id="fc84f-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>

 <span data-ttu-id="fc84f-105">Una manera útil de interpretar el principio es decir que se debe diseñar un tipo para que los cambios en los campos de ese tipo (nombre o tipo cambie) sin interrumpir el código que no sea para los miembros del tipo.</span><span class="sxs-lookup"><span data-stu-id="fc84f-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="fc84f-106">Esta interpretación implica inmediatamente que todos los campos deben ser privados.</span><span class="sxs-lookup"><span data-stu-id="fc84f-106">This interpretation immediately implies that all fields must be private.</span></span>

 <span data-ttu-id="fc84f-107">Se excluyen los campos de solo lectura constantes y estáticos de esta restricción estricta, ya que nunca es necesario cambiar estos campos, casi por definición.</span><span class="sxs-lookup"><span data-stu-id="fc84f-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>

 <span data-ttu-id="fc84f-108">❌ NO proporcione campos de instancia que sean públicos o protegidos.</span><span class="sxs-lookup"><span data-stu-id="fc84f-108">❌ DO NOT provide instance fields that are public or protected.</span></span>

 <span data-ttu-id="fc84f-109">Debe proporcionar propiedades para tener acceso a los campos en lugar de hacerlos públicos o protegidos.</span><span class="sxs-lookup"><span data-stu-id="fc84f-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>

 <span data-ttu-id="fc84f-110">✔️ usar campos constantes para las constantes que nunca cambiarán.</span><span class="sxs-lookup"><span data-stu-id="fc84f-110">✔️ DO use constant fields for constants that will never change.</span></span>

 <span data-ttu-id="fc84f-111">El compilador graba los valores de los campos const directamente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="fc84f-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="fc84f-112">Por lo tanto, los valores const no se pueden cambiar nunca sin el riesgo de que se interrumpa la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="fc84f-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>

 <span data-ttu-id="fc84f-113">✔️ usar campos estáticos públicos `readonly` para las instancias de objeto predefinidas.</span><span class="sxs-lookup"><span data-stu-id="fc84f-113">✔️ DO use public static `readonly` fields for predefined object instances.</span></span>

 <span data-ttu-id="fc84f-114">Si hay instancias predefinidas del tipo, declárela como campos estáticos de solo lectura públicos del propio tipo.</span><span class="sxs-lookup"><span data-stu-id="fc84f-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>

 <span data-ttu-id="fc84f-115">❌ NO asigne instancias de tipos mutables a `readonly` los campos.</span><span class="sxs-lookup"><span data-stu-id="fc84f-115">❌ DO NOT assign instances of mutable types to `readonly` fields.</span></span>

 <span data-ttu-id="fc84f-116">Un tipo mutable es un tipo con instancias que se pueden modificar una vez creadas las instancias.</span><span class="sxs-lookup"><span data-stu-id="fc84f-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="fc84f-117">Por ejemplo, las matrices, la mayoría de las colecciones y las secuencias son tipos mutables, pero <xref:System.Int32?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType> y <xref:System.String?displayProperty=nameWithType> son inmutables.</span><span class="sxs-lookup"><span data-stu-id="fc84f-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="fc84f-118">El modificador de solo lectura de un campo de tipo de referencia impide que la instancia almacenada en el campo se reemplace, pero no impide que los datos de instancia del campo se modifiquen llamando a los miembros que cambian la instancia.</span><span class="sxs-lookup"><span data-stu-id="fc84f-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>

 <span data-ttu-id="fc84f-119">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="fc84f-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="fc84f-120">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="fc84f-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="fc84f-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc84f-121">See also</span></span>

- [<span data-ttu-id="fc84f-122">Instrucciones para el diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="fc84f-122">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="fc84f-123">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="fc84f-123">Framework Design Guidelines</span></span>](index.md)
