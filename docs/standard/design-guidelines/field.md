---
title: "Diseño de campos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc3249518dd1e1c751de08c22d1c5eb4fa28dc6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="field-design"></a><span data-ttu-id="a7824-102">Diseño de campos</span><span class="sxs-lookup"><span data-stu-id="a7824-102">Field Design</span></span>
<span data-ttu-id="a7824-103">El principio de encapsulación es uno de los conceptos más importantes en el diseño orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="a7824-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="a7824-104">Este principio indica que los datos almacenados dentro de un objeto deben estar accesibles sólo para ese objeto.</span><span class="sxs-lookup"><span data-stu-id="a7824-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="a7824-105">Una forma útil de interpretar el principio consiste en indicar que un tipo debe diseñarse de modo que se pueden realizar cambios en los campos de ese tipo (cambios de nombre o tipo) sin interrumpir el código distinto para los miembros del tipo.</span><span class="sxs-lookup"><span data-stu-id="a7824-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="a7824-106">Esta interpretación inmediatamente implica que todos los campos deben ser privados.</span><span class="sxs-lookup"><span data-stu-id="a7824-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="a7824-107">Campos de solo lectura de constantes y estáticas se excluirán de esta restricción estricta, porque esos campos, casi por definición, nunca deben cambiar.</span><span class="sxs-lookup"><span data-stu-id="a7824-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="a7824-108">**X DO NOT** incluyen campos de instancia que son públicos o protegidos.</span><span class="sxs-lookup"><span data-stu-id="a7824-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="a7824-109">Debe proporcionar propiedades para tener acceso a campos en lugar de hacerlos público o protegido.</span><span class="sxs-lookup"><span data-stu-id="a7824-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="a7824-110">**✓ HACER** usar los campos constantes para las constantes que no cambia nunca.</span><span class="sxs-lookup"><span data-stu-id="a7824-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="a7824-111">El compilador lo grabe los valores de los campos const directamente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="a7824-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="a7824-112">Por lo tanto, los valores constantes nunca se pueden cambiar sin el riesgo de interrumpir la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="a7824-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="a7824-113">**✓ HACER** usar estáticos públicos `readonly` campos para instancias de objetos predefinidas.</span><span class="sxs-lookup"><span data-stu-id="a7824-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="a7824-114">Si no hay instancias predefinidas del tipo, declárelos como public campos estáticos de sólo lectura del tipo en Sí.</span><span class="sxs-lookup"><span data-stu-id="a7824-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="a7824-115">**X DO NOT** asignar instancias de tipos mutables a `readonly` campos.</span><span class="sxs-lookup"><span data-stu-id="a7824-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="a7824-116">Un tipo que mutable es un tipo con instancias que pueden modificarse después de que se crean instancias.</span><span class="sxs-lookup"><span data-stu-id="a7824-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="a7824-117">Por ejemplo, secuencias, mayoría de las colecciones y matrices son tipos mutables, pero <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, y <xref:System.String?displayProperty=nameWithType> todos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="a7824-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="a7824-118">El modificador de solo lectura en un campo de tipo de referencia impide que la instancia almacenada en el campo se reemplace, pero no impide que los datos de instancia del campo que se está modificando los miembros que realiza la llamada del cambio de la instancia.</span><span class="sxs-lookup"><span data-stu-id="a7824-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="a7824-119">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="a7824-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a7824-120">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="a7824-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7824-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7824-121">See Also</span></span>  
 [<span data-ttu-id="a7824-122">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="a7824-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="a7824-123">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a7824-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
