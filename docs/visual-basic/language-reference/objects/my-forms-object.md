---
title: My.Forms (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: d15765b7673f321d4362ceea0adb73959a7e7726
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44360484"
---
# <a name="myforms-object"></a><span data-ttu-id="e92fd-102">My.Forms (Objeto)</span><span class="sxs-lookup"><span data-stu-id="e92fd-102">My.Forms Object</span></span>
<span data-ttu-id="e92fd-103">Proporciona propiedades para tener acceso a una instancia de cada formulario de Windows que se declara en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="e92fd-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e92fd-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e92fd-104">Remarks</span></span>  
 <span data-ttu-id="e92fd-105">La `My.Forms` objeto proporciona una instancia de cada formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="e92fd-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="e92fd-106">El nombre de la propiedad es el mismo que el nombre del formulario que tiene acceso la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e92fd-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="e92fd-107">Puede tener acceso a los formularios proporcionados por el `My.Forms` objeto con el nombre del formulario, sin calificación.</span><span class="sxs-lookup"><span data-stu-id="e92fd-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="e92fd-108">Dado que el nombre de propiedad es igual al nombre de tipo del formulario, esto le permite tener acceso a un formulario como si tuviera una instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e92fd-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="e92fd-109">Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="e92fd-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="e92fd-110">La `My.Forms` objeto expone sólo los formularios asociados al proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="e92fd-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="e92fd-111">No proporciona acceso a formularios declarados en archivos DLL que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="e92fd-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="e92fd-112">Para obtener acceso a un formulario que proporciona un archivo DLL, debe usar el nombre completo del formulario, escrito como *DllName*. *FormName*.</span><span class="sxs-lookup"><span data-stu-id="e92fd-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="e92fd-113">Puede usar el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> propiedad para obtener una colección de los formularios abiertos de toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e92fd-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="e92fd-114">El objeto y sus propiedades están disponibles solo para las aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="e92fd-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e92fd-115">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e92fd-115">Properties</span></span>  
 <span data-ttu-id="e92fd-116">Cada propiedad de la `My.Forms` objeto proporciona acceso a una instancia de un formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="e92fd-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="e92fd-117">El nombre de la propiedad es el mismo que el nombre del formulario que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo de formulario.</span><span class="sxs-lookup"><span data-stu-id="e92fd-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e92fd-118">Si hay un conflicto de nombres, el nombre de propiedad para tener acceso a un formulario es *RootNamespace*_*Namespace*\_*FormName*.</span><span class="sxs-lookup"><span data-stu-id="e92fd-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="e92fd-119">Por ejemplo, considere dos formularios denominados `Form1.`si uno de estos formularios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, accedería a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="e92fd-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="e92fd-120">La `My.Forms` objeto proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio.</span><span class="sxs-lookup"><span data-stu-id="e92fd-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="e92fd-121">Para todas las demás formas, el `My.Forms` objeto crea una nueva instancia del formulario cuando se tiene acceso y lo almacena.</span><span class="sxs-lookup"><span data-stu-id="e92fd-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="e92fd-122">Intenta obtener acceso a esa propiedad devuelva esa instancia del formulario.</span><span class="sxs-lookup"><span data-stu-id="e92fd-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="e92fd-123">Puede eliminar mediante la asignación de un formulario `Nothing` a la propiedad de ese formulario.</span><span class="sxs-lookup"><span data-stu-id="e92fd-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="e92fd-124">Las llamadas de establecedor de propiedad el <xref:System.Windows.Forms.Form.Close%2A> método del formulario y, a continuación, asigna `Nothing` al valor almacenado.</span><span class="sxs-lookup"><span data-stu-id="e92fd-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="e92fd-125">Si asigna cualquier valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.</span><span class="sxs-lookup"><span data-stu-id="e92fd-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="e92fd-126">Puede probar si una propiedad de la `My.Forms` objeto almacena una instancia del formulario mediante el uso de la `Is` o `IsNot` operador.</span><span class="sxs-lookup"><span data-stu-id="e92fd-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="e92fd-127">Puede usar estos operadores para comprobar si el valor de la propiedad es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e92fd-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e92fd-128">Normalmente, el `Is` o `IsNot` operador tiene que leer el valor de la propiedad que se va a realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="e92fd-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="e92fd-129">Sin embargo, si la propiedad se almacena actualmente `Nothing`, la propiedad crea una nueva instancia del formulario y, a continuación, devuelve esa instancia.</span><span class="sxs-lookup"><span data-stu-id="e92fd-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="e92fd-130">Sin embargo, el compilador de Visual Basic trata las propiedades de la `My.Forms` objeto de forma diferente y permite la `Is` o `IsNot` operador para comprobar el estado de la propiedad sin cambiar su valor.</span><span class="sxs-lookup"><span data-stu-id="e92fd-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e92fd-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e92fd-131">Example</span></span>  
 <span data-ttu-id="e92fd-132">Este ejemplo cambia el título del valor predeterminado `SidebarMenu` formulario.</span><span class="sxs-lookup"><span data-stu-id="e92fd-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="e92fd-133">Para que funcione este ejemplo, el proyecto debe tener un formulario denominado `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="e92fd-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="e92fd-134">Este código funcionará solo en un proyecto de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e92fd-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e92fd-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e92fd-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="e92fd-136">Disponibilidad por tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="e92fd-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="e92fd-137">Tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="e92fd-137">Project type</span></span>|<span data-ttu-id="e92fd-138">Disponible</span><span class="sxs-lookup"><span data-stu-id="e92fd-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="e92fd-139">Aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="e92fd-139">Windows Application</span></span>|<span data-ttu-id="e92fd-140">**Sí**</span><span class="sxs-lookup"><span data-stu-id="e92fd-140">**Yes**</span></span>|  
|<span data-ttu-id="e92fd-141">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="e92fd-141">Class Library</span></span>|<span data-ttu-id="e92fd-142">No</span><span class="sxs-lookup"><span data-stu-id="e92fd-142">No</span></span>|  
|<span data-ttu-id="e92fd-143">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="e92fd-143">Console Application</span></span>|<span data-ttu-id="e92fd-144">No</span><span class="sxs-lookup"><span data-stu-id="e92fd-144">No</span></span>|  
|<span data-ttu-id="e92fd-145">Biblioteca de controles de Windows</span><span class="sxs-lookup"><span data-stu-id="e92fd-145">Windows Control Library</span></span>|<span data-ttu-id="e92fd-146">No</span><span class="sxs-lookup"><span data-stu-id="e92fd-146">No</span></span>|  
|<span data-ttu-id="e92fd-147">Biblioteca de controles Web</span><span class="sxs-lookup"><span data-stu-id="e92fd-147">Web Control Library</span></span>|<span data-ttu-id="e92fd-148">No</span><span class="sxs-lookup"><span data-stu-id="e92fd-148">No</span></span>|  
|<span data-ttu-id="e92fd-149">Servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="e92fd-149">Windows Service</span></span>|<span data-ttu-id="e92fd-150">No</span><span class="sxs-lookup"><span data-stu-id="e92fd-150">No</span></span>|  
|<span data-ttu-id="e92fd-151">Sitio web</span><span class="sxs-lookup"><span data-stu-id="e92fd-151">Web Site</span></span>|<span data-ttu-id="e92fd-152">No</span><span class="sxs-lookup"><span data-stu-id="e92fd-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e92fd-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="e92fd-153">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="e92fd-154">Objects</span><span class="sxs-lookup"><span data-stu-id="e92fd-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="e92fd-155">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="e92fd-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="e92fd-156">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="e92fd-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="e92fd-157">Acceso ad los formularios de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e92fd-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
