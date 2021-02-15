---
description: 'Más información acerca de: Diseño de campos'
title: Diseño de campos
ms.date: 10/22/2008
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
ms.openlocfilehash: 88df60c3050035221dc65429bbd543c71d5d69b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642050"
---
# <a name="field-design"></a><span data-ttu-id="2f4da-103">Diseño de campos</span><span class="sxs-lookup"><span data-stu-id="2f4da-103">Field Design</span></span>

<span data-ttu-id="2f4da-104">El principio de encapsulación es una de las nociones más importantes del diseño orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="2f4da-104">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="2f4da-105">Este principio indica que los datos almacenados dentro de un objeto solo deben ser accesibles para ese objeto.</span><span class="sxs-lookup"><span data-stu-id="2f4da-105">This principle states that data stored inside an object should be accessible only to that object.</span></span>

 <span data-ttu-id="2f4da-106">Una forma útil de interpretar el principio es decir que un tipo debe diseñarse de modo que los cambios en los campos de ese tipo (cambios de nombre o tipo) se puedan realizar sin romper el código que no sea para los miembros del tipo.</span><span class="sxs-lookup"><span data-stu-id="2f4da-106">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="2f4da-107">Esta interpretación implica inmediatamente que todos los campos deben ser privados.</span><span class="sxs-lookup"><span data-stu-id="2f4da-107">This interpretation immediately implies that all fields must be private.</span></span>

 <span data-ttu-id="2f4da-108">Se excluyen los campos de solo lectura constantes y estáticos de esta restricción estricta, ya que estos campos, casi por definición, nunca tienen que cambiar.</span><span class="sxs-lookup"><span data-stu-id="2f4da-108">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>

 <span data-ttu-id="2f4da-109">❌ NO proporcione campos de instancia que sean públicos o estén protegidos.</span><span class="sxs-lookup"><span data-stu-id="2f4da-109">❌ DO NOT provide instance fields that are public or protected.</span></span>

 <span data-ttu-id="2f4da-110">Debe proporcionar propiedades para tener acceso a los campos en lugar de convertirlos en públicos o protegidos.</span><span class="sxs-lookup"><span data-stu-id="2f4da-110">You should provide properties for accessing fields instead of making them public or protected.</span></span>

 <span data-ttu-id="2f4da-111">✔️ DEBE usar campos constantes para las constantes que nunca cambiarán.</span><span class="sxs-lookup"><span data-stu-id="2f4da-111">✔️ DO use constant fields for constants that will never change.</span></span>

 <span data-ttu-id="2f4da-112">El compilador graba los valores de los campos const directamente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="2f4da-112">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="2f4da-113">Por lo tanto, los valores const no se pueden cambiar nunca sin el riesgo de que se rompa la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="2f4da-113">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>

 <span data-ttu-id="2f4da-114">✔️ DEBE usar campos `readonly` estáticos públicos para instancias de objeto predefinidas.</span><span class="sxs-lookup"><span data-stu-id="2f4da-114">✔️ DO use public static `readonly` fields for predefined object instances.</span></span>

 <span data-ttu-id="2f4da-115">Si hay instancias predefinidas del tipo, declárelas como campos estáticos de solo lectura públicos del propio tipo.</span><span class="sxs-lookup"><span data-stu-id="2f4da-115">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>

 <span data-ttu-id="2f4da-116">❌ NO asigne instancias de tipos mutables a los campos `readonly`.</span><span class="sxs-lookup"><span data-stu-id="2f4da-116">❌ DO NOT assign instances of mutable types to `readonly` fields.</span></span>

 <span data-ttu-id="2f4da-117">Un tipo mutable es un tipo con instancias que se pueden modificar una vez creadas las instancias.</span><span class="sxs-lookup"><span data-stu-id="2f4da-117">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="2f4da-118">Por ejemplo, las matrices, la mayoría de las colecciones y las secuencias son tipos mutables, pero <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType> y <xref:System.String?displayProperty=nameWithType> son inmutables.</span><span class="sxs-lookup"><span data-stu-id="2f4da-118">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="2f4da-119">El modificador de solo lectura de un campo de tipo de referencia impide que la instancia almacenada en el campo se reemplace, pero no impide que los datos de instancia del campo se modifiquen mediante llamadas a los miembros que cambian la instancia.</span><span class="sxs-lookup"><span data-stu-id="2f4da-119">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>

 <span data-ttu-id="2f4da-120">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="2f4da-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="2f4da-121">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="2f4da-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="2f4da-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f4da-122">See also</span></span>

- [<span data-ttu-id="2f4da-123">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="2f4da-123">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="2f4da-124">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2f4da-124">Framework Design Guidelines</span></span>](index.md)
