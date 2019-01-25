---
title: Procedimiento Obtener acceso a miembros de un objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 5e91f1b99a17f4bbdc65a77ab26050ee57e96ac4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724848"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a><span data-ttu-id="e042d-102">Procedimiento Obtener acceso a miembros de un objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e042d-102">How to: Access Members of an Object (Visual Basic)</span></span>
<span data-ttu-id="e042d-103">Cuando haya una variable de objeto que hace referencia a un objeto, a menudo desea trabajar con los miembros de ese objeto, como sus métodos, propiedades, campos y eventos.</span><span class="sxs-lookup"><span data-stu-id="e042d-103">When you have an object variable that refers to an object, you often want to work with the members of that object, such as its methods, properties, fields, and events.</span></span> <span data-ttu-id="e042d-104">Por ejemplo, una vez haya creado un nuevo <xref:System.Windows.Forms.Form> objeto que desea establecer su <xref:System.Windows.Forms.Control.Text%2A> propiedad o llamada a su <xref:System.Windows.Forms.Control.Focus%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e042d-104">For example, once you have created a new <xref:System.Windows.Forms.Form> object, you might want to set its <xref:System.Windows.Forms.Control.Text%2A> property or call its <xref:System.Windows.Forms.Control.Focus%2A> method.</span></span>  
  
## <a name="accessing-members"></a><span data-ttu-id="e042d-105">Acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="e042d-105">Accessing Members</span></span>  
 <span data-ttu-id="e042d-106">Tener acceso a los miembros de un objeto a través de la variable que hace referencia a él.</span><span class="sxs-lookup"><span data-stu-id="e042d-106">You access an object's members through the variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object"></a><span data-ttu-id="e042d-107">Para obtener acceso a miembros de un objeto</span><span class="sxs-lookup"><span data-stu-id="e042d-107">To access members of an object</span></span>  
  
-   <span data-ttu-id="e042d-108">Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="e042d-108">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     <span data-ttu-id="e042d-109">Si el miembro es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), no es necesario una variable para acceder a él.</span><span class="sxs-lookup"><span data-stu-id="e042d-109">If the member is [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), you do not need a variable to access it.</span></span>  
  
## <a name="accessing-members-of-an-object-of-known-type"></a><span data-ttu-id="e042d-110">Acceso a miembros de un objeto de tipo conocido</span><span class="sxs-lookup"><span data-stu-id="e042d-110">Accessing Members of an Object of Known Type</span></span>  
 <span data-ttu-id="e042d-111">Si conoce el tipo de un objeto en tiempo de compilación, puede usar *enlace anticipado* para una variable que hace referencia a él.</span><span class="sxs-lookup"><span data-stu-id="e042d-111">If you know the type of an object at compile time, you can use *early binding* for a variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a><span data-ttu-id="e042d-112">Para obtener acceso a miembros de un objeto para el que se conoce el tipo en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="e042d-112">To access members of an object for which you know the type at compile time</span></span>  
  
1.  <span data-ttu-id="e042d-113">Declare la variable de objeto para ser del tipo del objeto que se va a asignar a la variable.</span><span class="sxs-lookup"><span data-stu-id="e042d-113">Declare the object variable to be of the type of the object you intend to assign to the variable.</span></span>  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     <span data-ttu-id="e042d-114">Con `Option Strict On`, puede asignar solo <xref:System.Windows.Forms.Form> objetos (o los objetos de un tipo derivan de <xref:System.Windows.Forms.Form>) a `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="e042d-114">With `Option Strict On`, you can assign only <xref:System.Windows.Forms.Form> objects (or objects of a type derived from <xref:System.Windows.Forms.Form>) to `extraForm`.</span></span> <span data-ttu-id="e042d-115">Si ha definido una clase o estructura con una ampliación `CType` conversión a <xref:System.Windows.Forms.Form>, también puede asignar esa clase o estructura a `extraForm`.</span><span class="sxs-lookup"><span data-stu-id="e042d-115">If you have defined a class or structure with a widening `CType` conversion to <xref:System.Windows.Forms.Form>, you can also assign that class or structure to `extraForm`.</span></span>  
  
2.  <span data-ttu-id="e042d-116">Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="e042d-116">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    extraForm.Show()  
    ```  
  
     <span data-ttu-id="e042d-117">Puede tener acceso a todos los métodos y propiedades específicas de la <xref:System.Windows.Forms.Form> (clase), independientemente de lo que el `Option Strict` es la configuración.</span><span class="sxs-lookup"><span data-stu-id="e042d-117">You can access all of the methods and properties specific to the <xref:System.Windows.Forms.Form> class, no matter what the `Option Strict` setting is.</span></span>  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a><span data-ttu-id="e042d-118">Acceso a miembros de un objeto de tipo desconocido</span><span class="sxs-lookup"><span data-stu-id="e042d-118">Accessing Members of an Object of Unknown Type</span></span>  
 <span data-ttu-id="e042d-119">Si no conoce el tipo de un objeto en tiempo de compilación, debe usar *enlace más tarde* para cualquier variable que hace referencia a él.</span><span class="sxs-lookup"><span data-stu-id="e042d-119">If you do not know the type of an object at compile time, you must use *late binding* for any variable that refers to it.</span></span>  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a><span data-ttu-id="e042d-120">Para obtener acceso a miembros de un objeto para el que se desconoce el tipo en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="e042d-120">To access members of an object for which you do not know the type at compile time</span></span>  
  
1.  <span data-ttu-id="e042d-121">Declare la variable de objeto de la [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="e042d-121">Declare the object variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="e042d-122">(Declarar una variable como `Object` es el mismo que su declaración como <xref:System.Object?displayProperty=nameWithType>.)</span><span class="sxs-lookup"><span data-stu-id="e042d-122">(Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.)</span></span>  
  
    ```  
    Dim someControl As Object  
    ```  
  
     <span data-ttu-id="e042d-123">Con `Option Strict On`, puede tener acceso a solo los miembros que se definen en el <xref:System.Object> clase.</span><span class="sxs-lookup"><span data-stu-id="e042d-123">With `Option Strict On`, you can access only the members that are defined on the <xref:System.Object> class.</span></span>  
  
2.  <span data-ttu-id="e042d-124">Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="e042d-124">Use the member-access operator (`.`) between the object variable name and the member name.</span></span>  
  
    ```  
    someControl.GetType()  
    ```  
  
     <span data-ttu-id="e042d-125">Para poder tener acceso a los miembros de cualquier objeto que se asigne a la variable de objeto, debe establecer `Option Strict Off`.</span><span class="sxs-lookup"><span data-stu-id="e042d-125">To be able to access the members of any object you assign to the object variable, you must set `Option Strict Off`.</span></span> <span data-ttu-id="e042d-126">Al hacerlo, el compilador no puede garantizar que un miembro determinado se expone mediante el objeto que se asigna a la variable.</span><span class="sxs-lookup"><span data-stu-id="e042d-126">When you do this, the compiler cannot guarantee that a given member is exposed by the object you assign to the variable.</span></span> <span data-ttu-id="e042d-127">Si el objeto no expone un miembro que intenta tener acceso, un <xref:System.MemberAccessException> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="e042d-127">If the object does not expose a member you attempt to access, a <xref:System.MemberAccessException> exception occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e042d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e042d-128">See also</span></span>
- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [<span data-ttu-id="e042d-129">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="e042d-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="e042d-130">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="e042d-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="e042d-131">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="e042d-131">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="e042d-132">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e042d-132">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
