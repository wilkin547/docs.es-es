---
title: Miembros (F#)
description: 'Obtenga información acerca de los miembros de objeto en el lenguaje de programación de F #.'
keywords: visual f#, f#, programación funcional
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e472f50a-4939-4e62-abbc-471f8f265790
ms.openlocfilehash: ca34c8d073594791ec268a85ad56f50cc6d9e435
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="members"></a><span data-ttu-id="1cc83-104">Miembros</span><span class="sxs-lookup"><span data-stu-id="1cc83-104">Members</span></span>

<span data-ttu-id="1cc83-105">En esta sección se describen los miembros de los tipos de objeto de F#.</span><span class="sxs-lookup"><span data-stu-id="1cc83-105">This section describes members of F# object types.</span></span>


## <a name="remarks"></a><span data-ttu-id="1cc83-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cc83-106">Remarks</span></span>
<span data-ttu-id="1cc83-107">Los *miembros* son características que forman parte de una definición de tipo y se declaran con la palabra clave `member`.</span><span class="sxs-lookup"><span data-stu-id="1cc83-107">*Members* are features that are part of a type definition and are declared with the `member` keyword.</span></span> <span data-ttu-id="1cc83-108">Los tipos de objeto de F#, como los registros, clases, uniones discriminadas, interfaces y estructuras, admiten miembros.</span><span class="sxs-lookup"><span data-stu-id="1cc83-108">F# object types such as records, classes, discriminated unions, interfaces, and structures support members.</span></span> <span data-ttu-id="1cc83-109">Para más información, vea [Registros](../records.md), [Clases](../classes.md), [Uniones discriminadas](../discriminated-Unions.md), [Interfaces](../interfaces.md) y [Estructuras](../structures.md).</span><span class="sxs-lookup"><span data-stu-id="1cc83-109">For more information, see [Records](../records.md), [Classes](../classes.md), [Discriminated Unions](../discriminated-Unions.md), [Interfaces](../interfaces.md), and [Structures](../structures.md).</span></span>

<span data-ttu-id="1cc83-110">Normalmente, los miembros componen la interfaz pública de un tipo, por lo que son públicos a menos que se especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="1cc83-110">Members typically make up the public interface for a type, which is why they are public unless otherwise specified.</span></span> <span data-ttu-id="1cc83-111">Los miembros también pueden declararse como privados o internos.</span><span class="sxs-lookup"><span data-stu-id="1cc83-111">Members can also be declared private or internal.</span></span> <span data-ttu-id="1cc83-112">Para más información, vea [Access Control](../access-Control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="1cc83-112">For more information, see [Access Control](../access-Control.md).</span></span> <span data-ttu-id="1cc83-113">También se pueden usar firmas de tipos para exponer o no determinados miembros de un tipo.</span><span class="sxs-lookup"><span data-stu-id="1cc83-113">Signatures for types can also be used to expose or not expose certain members of a type.</span></span> <span data-ttu-id="1cc83-114">Para más información, vea [Signatures](../signatures.md) (Firmas).</span><span class="sxs-lookup"><span data-stu-id="1cc83-114">For more information, see [Signatures](../signatures.md).</span></span>

<span data-ttu-id="1cc83-115">Los campos privados y los enlaces `do`, que se usan únicamente con las clases, no son miembros auténticos ya que nunca forman parte de la interfaz pública de un tipo y no se declaran con la palabra clave `member`, pero también se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="1cc83-115">Private fields and `do` bindings, which are used only with classes, are not true members, because they are never part of the public interface of a type and are not declared with the `member` keyword, but they are described in this section also.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1cc83-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1cc83-116">Related Topics</span></span>


|<span data-ttu-id="1cc83-117">Tema</span><span class="sxs-lookup"><span data-stu-id="1cc83-117">Topic</span></span>|<span data-ttu-id="1cc83-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cc83-118">Description</span></span>|
|-----|-----------|
|<span data-ttu-id="1cc83-119">[`let` Bindings in Classes](let-bindings-in-classes.md) (Enlaces `let` en clases)</span><span class="sxs-lookup"><span data-stu-id="1cc83-119">[`let` Bindings in Classes](let-bindings-in-classes.md)</span></span>|<span data-ttu-id="1cc83-120">Describe la definición de campos privados y funciones en las clases.</span><span class="sxs-lookup"><span data-stu-id="1cc83-120">Describes the definition of private fields and functions in classes.</span></span>|
|<span data-ttu-id="1cc83-121">[`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)</span><span class="sxs-lookup"><span data-stu-id="1cc83-121">[`do` Bindings in Classes](do-bindings-in-classes.md)</span></span>|<span data-ttu-id="1cc83-122">Describe la especificación de código de inicialización de objetos.</span><span class="sxs-lookup"><span data-stu-id="1cc83-122">Describes the specification of object initialization code.</span></span>|
|[<span data-ttu-id="1cc83-123">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1cc83-123">Properties</span></span>](properties.md)|<span data-ttu-id="1cc83-124">Describe los miembros de propiedad de las clases y otros tipos.</span><span class="sxs-lookup"><span data-stu-id="1cc83-124">Describes property members in classes and other types.</span></span>|
|[<span data-ttu-id="1cc83-125">Propiedades indexadas</span><span class="sxs-lookup"><span data-stu-id="1cc83-125">Indexed Properties</span></span>](indexed-properties.md)|<span data-ttu-id="1cc83-126">Describe propiedades similares a matrices de las clases y otros tipos.</span><span class="sxs-lookup"><span data-stu-id="1cc83-126">Describes array-like properties in classes and other types.</span></span>|
|[<span data-ttu-id="1cc83-127">Métodos</span><span class="sxs-lookup"><span data-stu-id="1cc83-127">Methods</span></span>](methods.md)|<span data-ttu-id="1cc83-128">Describe funciones que son miembros de un tipo.</span><span class="sxs-lookup"><span data-stu-id="1cc83-128">Describes functions that are members of a type.</span></span>|
|[<span data-ttu-id="1cc83-129">Constructores</span><span class="sxs-lookup"><span data-stu-id="1cc83-129">Constructors</span></span>](constructors.md)|<span data-ttu-id="1cc83-130">Describe funciones especiales que inicializan objetos de un tipo.</span><span class="sxs-lookup"><span data-stu-id="1cc83-130">Describes special functions that initialize objects of a type.</span></span>|
|[<span data-ttu-id="1cc83-131">Sobrecarga de operadores</span><span class="sxs-lookup"><span data-stu-id="1cc83-131">Operator Overloading</span></span>](../operator-overloading.md)|<span data-ttu-id="1cc83-132">Describe la definición de operadores personalizados para tipos.</span><span class="sxs-lookup"><span data-stu-id="1cc83-132">Describes the definition of customized operators for types.</span></span>|
|[<span data-ttu-id="1cc83-133">Eventos</span><span class="sxs-lookup"><span data-stu-id="1cc83-133">Events</span></span>](events.md)|<span data-ttu-id="1cc83-134">Describe la definición y la compatibilidad con el control de eventos en F#.</span><span class="sxs-lookup"><span data-stu-id="1cc83-134">Describes the definition of events and event handling support in F#.</span></span>|
|[<span data-ttu-id="1cc83-135">Campos explícitos: palabra clave `val`</span><span class="sxs-lookup"><span data-stu-id="1cc83-135">Explicit Fields: The `val` Keyword</span></span>](explicit-fields-the-val-keyword.md)|<span data-ttu-id="1cc83-136">Describe la definición de campos no inicializados en un tipo.</span><span class="sxs-lookup"><span data-stu-id="1cc83-136">Describes the definition of uninitialized fields in a type.</span></span>|
