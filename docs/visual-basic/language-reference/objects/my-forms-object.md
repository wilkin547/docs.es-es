---
description: 'Más información acerca de: My. Forms (objeto)'
title: My.Forms (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 18ef8ee475163ff7eb177dfee590d959a242a88e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774413"
---
# <a name="myforms-object"></a><span data-ttu-id="7f120-103">My.Forms (Objeto)</span><span class="sxs-lookup"><span data-stu-id="7f120-103">My.Forms Object</span></span>

<span data-ttu-id="7f120-104">Proporciona propiedades para obtener acceso a una instancia de cada Windows Forms declarado en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="7f120-104">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f120-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f120-105">Remarks</span></span>

<span data-ttu-id="7f120-106">El `My.Forms` objeto proporciona una instancia de cada formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="7f120-106">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="7f120-107">El nombre de la propiedad es el mismo que el nombre del formulario al que tiene acceso la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7f120-107">The name of the property is the same as the name of the form that the property accesses.</span></span>

<span data-ttu-id="7f120-108">Puede tener acceso a los formularios proporcionados por el `My.Forms` objeto utilizando el nombre del formulario, sin calificación.</span><span class="sxs-lookup"><span data-stu-id="7f120-108">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="7f120-109">Dado que el nombre de la propiedad es el mismo que el nombre de tipo del formulario, esto le permite tener acceso a un formulario como si tuviera una instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7f120-109">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="7f120-110">Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="7f120-110">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>

<span data-ttu-id="7f120-111">El `My.Forms` objeto expone solo los formularios asociados al proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="7f120-111">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="7f120-112">No proporciona acceso a los formularios declarados en los archivos DLL a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="7f120-112">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="7f120-113">Para tener acceso a un formulario que proporciona un archivo DLL, debe usar el nombre completo del formulario, escrito como *DllName*. *Nombreformulario*.</span><span class="sxs-lookup"><span data-stu-id="7f120-113">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>

<span data-ttu-id="7f120-114">Puede utilizar la <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> propiedad para obtener una colección de todos los formularios abiertos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f120-114">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>

<span data-ttu-id="7f120-115">El objeto y sus propiedades solo están disponibles para las aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="7f120-115">The object and its properties are available only for Windows applications.</span></span>

## <a name="properties"></a><span data-ttu-id="7f120-116">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7f120-116">Properties</span></span>

<span data-ttu-id="7f120-117">Cada propiedad del `My.Forms` objeto proporciona acceso a una instancia de un formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="7f120-117">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="7f120-118">El nombre de la propiedad es el mismo que el nombre del formulario al que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo del formulario.</span><span class="sxs-lookup"><span data-stu-id="7f120-118">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>

> [!NOTE]
> <span data-ttu-id="7f120-119">Si hay un conflicto de nombres, el nombre de la propiedad para tener acceso a un formulario es *RootNamespace* _ *espacio de nombres* \_ *formName*.</span><span class="sxs-lookup"><span data-stu-id="7f120-119">If there is a name collision, the property name to access a form is *RootNamespace* _ *Namespace*\_*FormName*.</span></span> <span data-ttu-id="7f120-120">Por ejemplo, considere dos formularios denominados `Form1.` si uno de estos formularios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1` , tendría acceso a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1` .</span><span class="sxs-lookup"><span data-stu-id="7f120-120">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>

<span data-ttu-id="7f120-121">El `My.Forms` objeto proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio.</span><span class="sxs-lookup"><span data-stu-id="7f120-121">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="7f120-122">En el caso de todos los demás formularios, el `My.Forms` objeto crea una nueva instancia del formulario cuando se tiene acceso a él y lo almacena.</span><span class="sxs-lookup"><span data-stu-id="7f120-122">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="7f120-123">Los intentos posteriores de obtener acceso a esa propiedad devuelven esa instancia del formulario.</span><span class="sxs-lookup"><span data-stu-id="7f120-123">Subsequent attempts to access that property return that instance of the form.</span></span>

<span data-ttu-id="7f120-124">Puede desechar un formulario asignando `Nothing` a la propiedad de ese formulario.</span><span class="sxs-lookup"><span data-stu-id="7f120-124">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="7f120-125">El establecedor de propiedad llama al <xref:System.Windows.Forms.Form.Close%2A> método del formulario y, a continuación, `Nothing` se asigna al valor almacenado.</span><span class="sxs-lookup"><span data-stu-id="7f120-125">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="7f120-126">Si asigna un valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.</span><span class="sxs-lookup"><span data-stu-id="7f120-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="7f120-127">Puede comprobar si una propiedad del `My.Forms` objeto almacena una instancia del formulario mediante el `Is` `IsNot` operador o.</span><span class="sxs-lookup"><span data-stu-id="7f120-127">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="7f120-128">Puede utilizar esos operadores para comprobar si el valor de la propiedad es `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="7f120-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>

> [!NOTE]
> <span data-ttu-id="7f120-129">Normalmente, el `Is` `IsNot` operador o tiene que leer el valor de la propiedad para realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="7f120-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="7f120-130">Sin embargo, si la propiedad almacena actualmente `Nothing` , la propiedad crea una nueva instancia del formulario y, a continuación, devuelve esa instancia.</span><span class="sxs-lookup"><span data-stu-id="7f120-130">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="7f120-131">Sin embargo, el compilador Visual Basic trata las propiedades del `My.Forms` objeto de forma diferente y permite `Is` que el `IsNot` operador OR Compruebe el estado de la propiedad sin modificar su valor.</span><span class="sxs-lookup"><span data-stu-id="7f120-131">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>

## <a name="example"></a><span data-ttu-id="7f120-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f120-132">Example</span></span>

<span data-ttu-id="7f120-133">En este ejemplo se cambia el título del `SidebarMenu` formulario predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f120-133">This example changes the title of the default `SidebarMenu` form.</span></span>

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

<span data-ttu-id="7f120-134">Para que este ejemplo funcione, el proyecto debe tener un formulario denominado `SidebarMenu` .</span><span class="sxs-lookup"><span data-stu-id="7f120-134">For this example to work, your project must have a form named `SidebarMenu`.</span></span>

<span data-ttu-id="7f120-135">Este código solo funcionará en un proyecto de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7f120-135">This code will work only in a Windows Application project.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f120-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f120-136">Requirements</span></span>

### <a name="availability-by-project-type"></a><span data-ttu-id="7f120-137">Disponibilidad por tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="7f120-137">Availability by Project Type</span></span>

|<span data-ttu-id="7f120-138">Tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="7f120-138">Project type</span></span>|<span data-ttu-id="7f120-139">Disponible</span><span class="sxs-lookup"><span data-stu-id="7f120-139">Available</span></span>|
|---|---|
|<span data-ttu-id="7f120-140">Aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="7f120-140">Windows Application</span></span>|<span data-ttu-id="7f120-141">**Sí**</span><span class="sxs-lookup"><span data-stu-id="7f120-141">**Yes**</span></span>|
|<span data-ttu-id="7f120-142">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7f120-142">Class Library</span></span>|<span data-ttu-id="7f120-143">No</span><span class="sxs-lookup"><span data-stu-id="7f120-143">No</span></span>|
|<span data-ttu-id="7f120-144">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="7f120-144">Console Application</span></span>|<span data-ttu-id="7f120-145">No</span><span class="sxs-lookup"><span data-stu-id="7f120-145">No</span></span>|
|<span data-ttu-id="7f120-146">Biblioteca de controles de Windows</span><span class="sxs-lookup"><span data-stu-id="7f120-146">Windows Control Library</span></span>|<span data-ttu-id="7f120-147">No</span><span class="sxs-lookup"><span data-stu-id="7f120-147">No</span></span>|
|<span data-ttu-id="7f120-148">Biblioteca de controles web</span><span class="sxs-lookup"><span data-stu-id="7f120-148">Web Control Library</span></span>|<span data-ttu-id="7f120-149">No</span><span class="sxs-lookup"><span data-stu-id="7f120-149">No</span></span>|
|<span data-ttu-id="7f120-150">Servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="7f120-150">Windows Service</span></span>|<span data-ttu-id="7f120-151">No</span><span class="sxs-lookup"><span data-stu-id="7f120-151">No</span></span>|
|<span data-ttu-id="7f120-152">Sitio web</span><span class="sxs-lookup"><span data-stu-id="7f120-152">Web Site</span></span>|<span data-ttu-id="7f120-153">No</span><span class="sxs-lookup"><span data-stu-id="7f120-153">No</span></span>|

## <a name="see-also"></a><span data-ttu-id="7f120-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f120-154">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="7f120-155">Objetos</span><span class="sxs-lookup"><span data-stu-id="7f120-155">Objects</span></span>](index.md)
- [<span data-ttu-id="7f120-156">Operador Is</span><span class="sxs-lookup"><span data-stu-id="7f120-156">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="7f120-157">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="7f120-157">IsNot Operator</span></span>](../operators/isnot-operator.md)
- [<span data-ttu-id="7f120-158">Acceso ad los formularios de la aplicación</span><span class="sxs-lookup"><span data-stu-id="7f120-158">Accessing Application Forms</span></span>](../../developing-apps/programming/accessing-application-forms.md)
