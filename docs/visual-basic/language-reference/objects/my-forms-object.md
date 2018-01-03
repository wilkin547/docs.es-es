---
title: My.Forms (Objeto)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords: My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fe548caacf2c8e7498e3b7abc814b4f89af9b3d6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="myforms-object"></a><span data-ttu-id="bc639-102">My.Forms (Objeto)</span><span class="sxs-lookup"><span data-stu-id="bc639-102">My.Forms Object</span></span>
<span data-ttu-id="bc639-103">Proporciona propiedades para tener acceso a una instancia de cada formulario Windows Forms declarado en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="bc639-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc639-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc639-104">Remarks</span></span>  
 <span data-ttu-id="bc639-105">La `My.Forms` objeto proporciona una instancia de cada formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="bc639-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="bc639-106">El nombre de la propiedad es el mismo que el nombre del formulario que tiene acceso la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bc639-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="bc639-107">Puede tener acceso a los formularios proporcionados por el `My.Forms` objeto mediante el nombre del formulario, sin calificación.</span><span class="sxs-lookup"><span data-stu-id="bc639-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="bc639-108">Dado que el nombre de propiedad es el mismo que el nombre de tipo del formulario, esto le permite tener acceso a un formulario como si tuviera una instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bc639-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="bc639-109">Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="bc639-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="bc639-110">La `My.Forms` objeto expone sólo los formularios asociados al proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="bc639-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="bc639-111">No proporciona acceso a formularios declarados en archivos DLL que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="bc639-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="bc639-112">Para obtener acceso a un formulario que proporciona un archivo DLL, debe usar el nombre completo del formulario, escrito como *nombre dll*. *FormName*.</span><span class="sxs-lookup"><span data-stu-id="bc639-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="bc639-113">Puede usar el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> propiedad para obtener una colección de formularios abiertos de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bc639-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="bc639-114">El objeto y sus propiedades solo están disponibles para las aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="bc639-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bc639-115">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bc639-115">Properties</span></span>  
 <span data-ttu-id="bc639-116">Cada propiedad de la `My.Forms` objeto proporciona acceso a una instancia de un formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="bc639-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="bc639-117">El nombre de la propiedad es el mismo que el nombre del formulario que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo de formulario.</span><span class="sxs-lookup"><span data-stu-id="bc639-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc639-118">Si hay un conflicto de nombres, el nombre de propiedad para tener acceso a un formulario es *RootNamespace*_*Namespace*\_*nombreformulario*.</span><span class="sxs-lookup"><span data-stu-id="bc639-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="bc639-119">Por ejemplo, considere dos formularios denominados `Form1.`si uno de estos formularios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, accedería a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="bc639-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="bc639-120">La `My.Forms` objeto proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio.</span><span class="sxs-lookup"><span data-stu-id="bc639-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="bc639-121">Para todas las demás formas, el `My.Forms` objeto crea una nueva instancia del formulario cuando se tiene acceso y lo almacena.</span><span class="sxs-lookup"><span data-stu-id="bc639-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="bc639-122">Intenta obtener acceso a esa propiedad devuelve esa instancia del formulario.</span><span class="sxs-lookup"><span data-stu-id="bc639-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="bc639-123">Puede desechar un formulario mediante la asignación de `Nothing` a la propiedad de ese formulario.</span><span class="sxs-lookup"><span data-stu-id="bc639-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="bc639-124">Las llamadas de establecedor de propiedad el <xref:System.Windows.Forms.Form.Close%2A> método del formulario y, a continuación, asigna `Nothing` al valor almacenado.</span><span class="sxs-lookup"><span data-stu-id="bc639-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="bc639-125">Si asigna cualquier valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.</span><span class="sxs-lookup"><span data-stu-id="bc639-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="bc639-126">Puede probar si una propiedad de la `My.Forms` objeto almacena una instancia del formulario mediante la `Is` o `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="bc639-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="bc639-127">Puede usar los operadores para comprobar si el valor de la propiedad es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="bc639-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc639-128">Normalmente, el `Is` o `IsNot` operador tiene que leer el valor de la propiedad que se va a realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="bc639-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="bc639-129">Sin embargo, si la propiedad almacena actualmente `Nothing`, la propiedad se crea una nueva instancia del formulario y, a continuación, devuelve esa instancia.</span><span class="sxs-lookup"><span data-stu-id="bc639-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="bc639-130">Sin embargo, el compilador de Visual Basic trata las propiedades de la `My.Forms` objeto de manera diferente y permite la `Is` o `IsNot` operador para comprobar el estado de la propiedad sin modificar su valor.</span><span class="sxs-lookup"><span data-stu-id="bc639-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc639-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc639-131">Example</span></span>  
 <span data-ttu-id="bc639-132">Este ejemplo cambia el título del valor predeterminado `SidebarMenu` formulario.</span><span class="sxs-lookup"><span data-stu-id="bc639-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="bc639-133">Para que funcione este ejemplo, el proyecto debe tener un formulario denominado `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="bc639-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="bc639-134">Este código funcionará solamente en un proyecto de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="bc639-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc639-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc639-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="bc639-136">Disponibilidad por tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="bc639-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="bc639-137">Tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="bc639-137">Project type</span></span>|<span data-ttu-id="bc639-138">Disponible</span><span class="sxs-lookup"><span data-stu-id="bc639-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="bc639-139">Aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="bc639-139">Windows Application</span></span>|<span data-ttu-id="bc639-140">**Sí**</span><span class="sxs-lookup"><span data-stu-id="bc639-140">**Yes**</span></span>|  
|<span data-ttu-id="bc639-141">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="bc639-141">Class Library</span></span>|<span data-ttu-id="bc639-142">No</span><span class="sxs-lookup"><span data-stu-id="bc639-142">No</span></span>|  
|<span data-ttu-id="bc639-143">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="bc639-143">Console Application</span></span>|<span data-ttu-id="bc639-144">No</span><span class="sxs-lookup"><span data-stu-id="bc639-144">No</span></span>|  
|<span data-ttu-id="bc639-145">Biblioteca de controles de Windows</span><span class="sxs-lookup"><span data-stu-id="bc639-145">Windows Control Library</span></span>|<span data-ttu-id="bc639-146">No</span><span class="sxs-lookup"><span data-stu-id="bc639-146">No</span></span>|  
|<span data-ttu-id="bc639-147">Biblioteca de controles Web</span><span class="sxs-lookup"><span data-stu-id="bc639-147">Web Control Library</span></span>|<span data-ttu-id="bc639-148">No</span><span class="sxs-lookup"><span data-stu-id="bc639-148">No</span></span>|  
|<span data-ttu-id="bc639-149">Servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="bc639-149">Windows Service</span></span>|<span data-ttu-id="bc639-150">No</span><span class="sxs-lookup"><span data-stu-id="bc639-150">No</span></span>|  
|<span data-ttu-id="bc639-151">Sitio web</span><span class="sxs-lookup"><span data-stu-id="bc639-151">Web Site</span></span>|<span data-ttu-id="bc639-152">No</span><span class="sxs-lookup"><span data-stu-id="bc639-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc639-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc639-153">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="bc639-154">Objects</span><span class="sxs-lookup"><span data-stu-id="bc639-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="bc639-155">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="bc639-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="bc639-156">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="bc639-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="bc639-157">Acceso ad los formularios de la aplicación</span><span class="sxs-lookup"><span data-stu-id="bc639-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
