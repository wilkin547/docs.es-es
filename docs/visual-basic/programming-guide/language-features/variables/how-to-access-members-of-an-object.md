---
description: 'Más información acerca de cómo: obtener acceso a los miembros de un objeto (Visual Basic)'
title: Procedimiento para obtener acceso a los miembros de un objeto
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: b4aed213bbe520b7b7027acc146d0973f7273fd1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435530"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="2a314-103">Cómo: Obtener acceso a los miembros de un objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a314-103">How to: Access Members of an Object (Visual Basic)</span></span>

<span data-ttu-id="2a314-104">Si tiene una variable de objeto que hace referencia a un objeto, a menudo desea trabajar con los miembros de ese objeto, como sus métodos, propiedades, campos y eventos.</span><span class="sxs-lookup"><span data-stu-id="2a314-104">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="2a314-105">Por ejemplo, una vez que haya creado un nuevo <xref:System.Windows.Forms.Form> objeto, es posible que desee establecer su <xref:System.Windows.Forms.Control.Text%2A> propiedad o llamar a su <xref:System.Windows.Forms.Control.Focus%2A> método.</span><span class="sxs-lookup"><span data-stu-id="2a314-105">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>

## <a name="accessing-members"></a><span data-ttu-id="2a314-106">Obtener acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="2a314-106">Accessing Members</span></span>

<span data-ttu-id="2a314-107">Puede tener acceso a los miembros de un objeto a través de la variable que hace referencia a él.</span><span class="sxs-lookup"><span data-stu-id="2a314-107">You access an object's members through the variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="2a314-108">Para tener acceso a los miembros de un objeto</span><span class="sxs-lookup"><span data-stu-id="2a314-108">To access members of an object</span></span>

- <span data-ttu-id="2a314-109">Use el operador de acceso a miembros ( `.` ) entre el nombre de la variable de objeto y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="2a314-109">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    currentText = newForm.Text
    ```

    <span data-ttu-id="2a314-110">Si el miembro es [compartido](../../../language-reference/modifiers/shared.md), no necesita una variable para tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="2a314-110">If the member is [Shared](../../../language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>

## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="2a314-111">Obtener acceso a miembros de un objeto de tipo conocido</span><span class="sxs-lookup"><span data-stu-id="2a314-111">Accessing Members of an Object of Known Type</span></span>

<span data-ttu-id="2a314-112">Si conoce el tipo de un objeto en tiempo de compilación, puede usar el *enlace temprano* para una variable que haga referencia a él.</span><span class="sxs-lookup"><span data-stu-id="2a314-112">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="2a314-113">Para obtener acceso a los miembros de un objeto para el que conoce el tipo en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="2a314-113">To access members of an object for which you know the type at compile time</span></span>

1. <span data-ttu-id="2a314-114">Declare la variable de objeto para que sea del tipo del objeto que desea asignar a la variable.</span><span class="sxs-lookup"><span data-stu-id="2a314-114">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    <span data-ttu-id="2a314-115">Con `Option Strict On` , solo puede asignar <xref:System.Windows.Forms.Form> objetos (u objetos de un tipo derivado de <xref:System.Windows.Forms.Form> ) a `extraForm` .</span><span class="sxs-lookup"><span data-stu-id="2a314-115">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="2a314-116">Si ha definido una clase o estructura con una conversión de ampliación `CType` a <xref:System.Windows.Forms.Form> , también puede asignar esa clase o estructura a `extraForm` .</span><span class="sxs-lookup"><span data-stu-id="2a314-116">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>

2. <span data-ttu-id="2a314-117">Use el operador de acceso a miembros ( `.` ) entre el nombre de la variable de objeto y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="2a314-117">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    extraForm.Show()
    ```

    <span data-ttu-id="2a314-118">Puede tener acceso a todos los métodos y propiedades específicos de la <xref:System.Windows.Forms.Form> clase, con independencia de cuál `Option Strict` sea la configuración.</span><span class="sxs-lookup"><span data-stu-id="2a314-118">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>

## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="2a314-119">Obtener acceso a miembros de un objeto de tipo desconocido</span><span class="sxs-lookup"><span data-stu-id="2a314-119">Accessing Members of an Object of Unknown Type</span></span>

<span data-ttu-id="2a314-120">Si no conoce el tipo de un objeto en tiempo de compilación, debe utilizar el enlace en tiempo de *ejecución* para cualquier variable que haga referencia a él.</span><span class="sxs-lookup"><span data-stu-id="2a314-120">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="2a314-121">Para tener acceso a los miembros de un objeto para el que no conoce el tipo en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="2a314-121">To access members of an object for which you do not know the type at compile time</span></span>

1. <span data-ttu-id="2a314-122">Declare la variable de objeto para que sea del [tipo de datos Object](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="2a314-122">Declare the object variable to be of the [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="2a314-123">(Declarar una variable como `Object` es igual que la declaración como <xref:System.Object?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="2a314-123">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>

    ```vb
    Dim someControl As Object
    ```

    <span data-ttu-id="2a314-124">Con `Option Strict On` , solo puede tener acceso a los miembros que se definen en la <xref:System.Object> clase.</span><span class="sxs-lookup"><span data-stu-id="2a314-124">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>

2. <span data-ttu-id="2a314-125">Use el operador de acceso a miembros ( `.` ) entre el nombre de la variable de objeto y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="2a314-125">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>

    ```vb
    someControl.GetType()
    ```

    <span data-ttu-id="2a314-126">Para poder tener acceso a los miembros de cualquier objeto que asigne a la variable de objeto, debe establecer `Option Strict Off` .</span><span class="sxs-lookup"><span data-stu-id="2a314-126">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="2a314-127">Al hacerlo, el compilador no puede garantizar que un miembro determinado esté expuesto por el objeto que se asigna a la variable.</span><span class="sxs-lookup"><span data-stu-id="2a314-127">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="2a314-128">Si el objeto no expone un miembro al que se intenta tener acceso, <xref:System.MemberAccessException> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="2a314-128">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a314-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a314-129">See also</span></span>

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="2a314-130">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="2a314-130">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="2a314-131">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="2a314-131">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="2a314-132">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="2a314-132">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="2a314-133">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2a314-133">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
