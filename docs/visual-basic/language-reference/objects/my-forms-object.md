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
ms.openlocfilehash: a5aa7af1f07a29660335d968c1ecc17be5f8beec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="myforms-object"></a><span data-ttu-id="79c8b-102">My.Forms (Objeto)</span><span class="sxs-lookup"><span data-stu-id="79c8b-102">My.Forms Object</span></span>
<span data-ttu-id="79c8b-103">Proporciona propiedades para tener acceso a una instancia de cada formulario Windows Forms declarado en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="79c8b-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79c8b-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79c8b-104">Remarks</span></span>  
 <span data-ttu-id="79c8b-105">La `My.Forms` objeto proporciona una instancia de cada formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="79c8b-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="79c8b-106">El nombre de la propiedad es el mismo que el nombre del formulario que tiene acceso la propiedad.</span><span class="sxs-lookup"><span data-stu-id="79c8b-106">The name of the property is the same as the name of the form that the property accesses.</span></span> <span data-ttu-id="79c8b-107">Para obtener información acerca de cómo agregar formas a un proyecto, vea [Cómo: agregar Windows Forms a un proyecto](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="79c8b-107">For information about adding forms to a project, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
 <span data-ttu-id="79c8b-108">Puede tener acceso a los formularios proporcionados por el `My.Forms` objeto mediante el nombre del formulario, sin calificación.</span><span class="sxs-lookup"><span data-stu-id="79c8b-108">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="79c8b-109">Dado que el nombre de propiedad es el mismo que el nombre de tipo del formulario, esto le permite tener acceso a un formulario como si tuviera una instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="79c8b-109">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="79c8b-110">Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="79c8b-110">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="79c8b-111">La `My.Forms` objeto expone sólo los formularios asociados al proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="79c8b-111">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="79c8b-112">No proporciona acceso a formularios declarados en archivos DLL que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="79c8b-112">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="79c8b-113">Para obtener acceso a un formulario que proporciona un archivo DLL, debe usar el nombre completo del formulario, escrito como *nombre dll*. *FormName*.</span><span class="sxs-lookup"><span data-stu-id="79c8b-113">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="79c8b-114">Puede usar el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> propiedad para obtener una colección de formularios abiertos de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="79c8b-114">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="79c8b-115">El objeto y sus propiedades solo están disponibles para las aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="79c8b-115">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="79c8b-116">Propiedades</span><span class="sxs-lookup"><span data-stu-id="79c8b-116">Properties</span></span>  
 <span data-ttu-id="79c8b-117">Cada propiedad de la `My.Forms` objeto proporciona acceso a una instancia de un formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="79c8b-117">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="79c8b-118">El nombre de la propiedad es el mismo que el nombre del formulario que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo de formulario.</span><span class="sxs-lookup"><span data-stu-id="79c8b-118">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79c8b-119">Si hay un conflicto de nombres, el nombre de propiedad para tener acceso a un formulario es *RootNamespace*_*Namespace*\_*nombreformulario*.</span><span class="sxs-lookup"><span data-stu-id="79c8b-119">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="79c8b-120">Por ejemplo, considere dos formularios denominados `Form1.`si uno de estos formularios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, accedería a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="79c8b-120">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="79c8b-121">La `My.Forms` objeto proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio.</span><span class="sxs-lookup"><span data-stu-id="79c8b-121">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="79c8b-122">Para todas las demás formas, el `My.Forms` objeto crea una nueva instancia del formulario cuando se tiene acceso y lo almacena.</span><span class="sxs-lookup"><span data-stu-id="79c8b-122">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="79c8b-123">Intenta obtener acceso a esa propiedad devuelve esa instancia del formulario.</span><span class="sxs-lookup"><span data-stu-id="79c8b-123">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="79c8b-124">Puede desechar un formulario mediante la asignación de `Nothing` a la propiedad de ese formulario.</span><span class="sxs-lookup"><span data-stu-id="79c8b-124">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="79c8b-125">Las llamadas de establecedor de propiedad el <xref:System.Windows.Forms.Form.Close%2A> método del formulario y, a continuación, asigna `Nothing` al valor almacenado.</span><span class="sxs-lookup"><span data-stu-id="79c8b-125">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="79c8b-126">Si asigna cualquier valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.</span><span class="sxs-lookup"><span data-stu-id="79c8b-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="79c8b-127">Puede probar si una propiedad de la `My.Forms` objeto almacena una instancia del formulario mediante la `Is` o `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="79c8b-127">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="79c8b-128">Puede usar los operadores para comprobar si el valor de la propiedad es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="79c8b-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79c8b-129">Normalmente, el `Is` o `IsNot` operador tiene que leer el valor de la propiedad que se va a realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="79c8b-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="79c8b-130">Sin embargo, si la propiedad almacena actualmente `Nothing`, la propiedad se crea una nueva instancia del formulario y, a continuación, devuelve esa instancia.</span><span class="sxs-lookup"><span data-stu-id="79c8b-130">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="79c8b-131">Sin embargo, el compilador de Visual Basic trata las propiedades de la `My.Forms` objeto de manera diferente y permite la `Is` o `IsNot` operador para comprobar el estado de la propiedad sin modificar su valor.</span><span class="sxs-lookup"><span data-stu-id="79c8b-131">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79c8b-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79c8b-132">Example</span></span>  
 <span data-ttu-id="79c8b-133">Este ejemplo cambia el título del valor predeterminado `SidebarMenu` formulario.</span><span class="sxs-lookup"><span data-stu-id="79c8b-133">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="79c8b-134">Para que funcione este ejemplo, el proyecto debe tener un formulario denominado `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="79c8b-134">For this example to work, your project must have a form named `SidebarMenu`.</span></span> <span data-ttu-id="79c8b-135">Para obtener más información, consulte [Cómo: agregar Windows Forms a un proyecto](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="79c8b-135">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
 <span data-ttu-id="79c8b-136">Este código funcionará solamente en un proyecto de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="79c8b-136">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79c8b-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79c8b-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="79c8b-138">Disponibilidad por tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="79c8b-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="79c8b-139">Tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="79c8b-139">Project type</span></span>|<span data-ttu-id="79c8b-140">Disponible</span><span class="sxs-lookup"><span data-stu-id="79c8b-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="79c8b-141">Aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="79c8b-141">Windows Application</span></span>|<span data-ttu-id="79c8b-142">**Sí**</span><span class="sxs-lookup"><span data-stu-id="79c8b-142">**Yes**</span></span>|  
|<span data-ttu-id="79c8b-143">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="79c8b-143">Class Library</span></span>|<span data-ttu-id="79c8b-144">No</span><span class="sxs-lookup"><span data-stu-id="79c8b-144">No</span></span>|  
|<span data-ttu-id="79c8b-145">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="79c8b-145">Console Application</span></span>|<span data-ttu-id="79c8b-146">No</span><span class="sxs-lookup"><span data-stu-id="79c8b-146">No</span></span>|  
|<span data-ttu-id="79c8b-147">Biblioteca de controles de Windows</span><span class="sxs-lookup"><span data-stu-id="79c8b-147">Windows Control Library</span></span>|<span data-ttu-id="79c8b-148">No</span><span class="sxs-lookup"><span data-stu-id="79c8b-148">No</span></span>|  
|<span data-ttu-id="79c8b-149">Biblioteca de controles Web</span><span class="sxs-lookup"><span data-stu-id="79c8b-149">Web Control Library</span></span>|<span data-ttu-id="79c8b-150">No</span><span class="sxs-lookup"><span data-stu-id="79c8b-150">No</span></span>|  
|<span data-ttu-id="79c8b-151">Servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="79c8b-151">Windows Service</span></span>|<span data-ttu-id="79c8b-152">No</span><span class="sxs-lookup"><span data-stu-id="79c8b-152">No</span></span>|  
|<span data-ttu-id="79c8b-153">Sitio web</span><span class="sxs-lookup"><span data-stu-id="79c8b-153">Web Site</span></span>|<span data-ttu-id="79c8b-154">No</span><span class="sxs-lookup"><span data-stu-id="79c8b-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79c8b-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="79c8b-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="79c8b-156">Objects</span><span class="sxs-lookup"><span data-stu-id="79c8b-156">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="79c8b-157">Cómo: agregar formularios Windows Forms a un proyecto</span><span class="sxs-lookup"><span data-stu-id="79c8b-157">How to: Add Windows Forms to a Project</span></span>](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)  
 [<span data-ttu-id="79c8b-158">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="79c8b-158">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="79c8b-159">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="79c8b-159">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="79c8b-160">Acceso ad los formularios de la aplicación</span><span class="sxs-lookup"><span data-stu-id="79c8b-160">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
