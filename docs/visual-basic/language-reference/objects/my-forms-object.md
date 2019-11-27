---
title: My.Forms (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: db86704fdc8120ccac5f4489c80a515834ad888f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350370"
---
# <a name="myforms-object"></a><span data-ttu-id="1e0b7-102">My.Forms (Objeto)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-102">My.Forms Object</span></span>

<span data-ttu-id="1e0b7-103">Proporciona propiedades para obtener acceso a una instancia de cada Windows Forms declarado en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e0b7-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e0b7-104">Remarks</span></span>

<span data-ttu-id="1e0b7-105">El objeto `My.Forms` proporciona una instancia de cada formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="1e0b7-106">El nombre de la propiedad es el mismo que el nombre del formulario al que tiene acceso la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-106">The name of the property is the same as the name of the form that the property accesses.</span></span>

<span data-ttu-id="1e0b7-107">Puede tener acceso a los formularios proporcionados por el objeto `My.Forms` utilizando el nombre del formulario, sin calificación.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="1e0b7-108">Dado que el nombre de la propiedad es el mismo que el nombre de tipo del formulario, esto le permite tener acceso a un formulario como si tuviera una instancia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="1e0b7-109">Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>

<span data-ttu-id="1e0b7-110">El objeto `My.Forms` expone solo los formularios asociados al proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="1e0b7-111">No proporciona acceso a los formularios declarados en los archivos DLL a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="1e0b7-112">Para tener acceso a un formulario que proporciona un archivo DLL, debe usar el nombre completo del formulario, escrito como *DllName*. *Nombreformulario*.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>

<span data-ttu-id="1e0b7-113">Puede usar la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> para obtener una colección de todos los formularios abiertos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>

<span data-ttu-id="1e0b7-114">El objeto y sus propiedades solo están disponibles para las aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-114">The object and its properties are available only for Windows applications.</span></span>

## <a name="properties"></a><span data-ttu-id="1e0b7-115">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1e0b7-115">Properties</span></span>

<span data-ttu-id="1e0b7-116">Cada propiedad del objeto `My.Forms` proporciona acceso a una instancia de un formulario en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="1e0b7-117">El nombre de la propiedad es el mismo que el nombre del formulario al que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo del formulario.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>

> [!NOTE]
> <span data-ttu-id="1e0b7-118">Si hay un conflicto de nombres, el nombre de la propiedad para tener acceso a un formulario es *RootNamespace*_*namespace*\_*formName*.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="1e0b7-119">Por ejemplo, considere dos formularios denominados `Form1.`si uno de estos formularios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, tendría acceso a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>

<span data-ttu-id="1e0b7-120">El objeto `My.Forms` proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="1e0b7-121">En el caso de todos los demás formularios, el objeto `My.Forms` crea una instancia nueva del formulario cuando se tiene acceso a ella y la almacena.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="1e0b7-122">Los intentos posteriores de obtener acceso a esa propiedad devuelven esa instancia del formulario.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-122">Subsequent attempts to access that property return that instance of the form.</span></span>

<span data-ttu-id="1e0b7-123">Puede desechar un formulario asignando `Nothing` a la propiedad de ese formulario.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="1e0b7-124">El establecedor de propiedad llama al método <xref:System.Windows.Forms.Form.Close%2A> del formulario y, a continuación, asigna `Nothing` al valor almacenado.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="1e0b7-125">Si asigna un valor distinto de `Nothing` a la propiedad, el establecedor produce una excepción de <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="1e0b7-126">Puede comprobar si una propiedad del objeto `My.Forms` almacena una instancia del formulario mediante el operador `Is` o `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="1e0b7-127">Puede utilizar esos operadores para comprobar si el valor de la propiedad es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>

> [!NOTE]
> <span data-ttu-id="1e0b7-128">Normalmente, el operador `Is` o `IsNot` tiene que leer el valor de la propiedad para realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="1e0b7-129">Sin embargo, si la propiedad almacena actualmente `Nothing`, la propiedad crea una nueva instancia del formulario y, a continuación, devuelve esa instancia.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="1e0b7-130">Sin embargo, el compilador Visual Basic trata las propiedades del objeto `My.Forms` de forma diferente y permite que el operador `Is` o `IsNot` Compruebe el estado de la propiedad sin modificar su valor.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>

## <a name="example"></a><span data-ttu-id="1e0b7-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e0b7-131">Example</span></span>

<span data-ttu-id="1e0b7-132">En este ejemplo se cambia el título del formulario `SidebarMenu` predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-132">This example changes the title of the default `SidebarMenu` form.</span></span>

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

<span data-ttu-id="1e0b7-133">Para que este ejemplo funcione, el proyecto debe tener un formulario denominado `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>

<span data-ttu-id="1e0b7-134">Este código solo funcionará en un proyecto de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1e0b7-134">This code will work only in a Windows Application project.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e0b7-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e0b7-135">Requirements</span></span>

### <a name="availability-by-project-type"></a><span data-ttu-id="1e0b7-136">Disponibilidad por tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="1e0b7-136">Availability by Project Type</span></span>

|<span data-ttu-id="1e0b7-137">Tipo de proyecto</span><span class="sxs-lookup"><span data-stu-id="1e0b7-137">Project type</span></span>|<span data-ttu-id="1e0b7-138">Disponible</span><span class="sxs-lookup"><span data-stu-id="1e0b7-138">Available</span></span>|
|---|---|
|<span data-ttu-id="1e0b7-139">Aplicación de Windows</span><span class="sxs-lookup"><span data-stu-id="1e0b7-139">Windows Application</span></span>|<span data-ttu-id="1e0b7-140">**Sí**</span><span class="sxs-lookup"><span data-stu-id="1e0b7-140">**Yes**</span></span>|
|<span data-ttu-id="1e0b7-141">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="1e0b7-141">Class Library</span></span>|<span data-ttu-id="1e0b7-142">No</span><span class="sxs-lookup"><span data-stu-id="1e0b7-142">No</span></span>|
|<span data-ttu-id="1e0b7-143">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="1e0b7-143">Console Application</span></span>|<span data-ttu-id="1e0b7-144">No</span><span class="sxs-lookup"><span data-stu-id="1e0b7-144">No</span></span>|
|<span data-ttu-id="1e0b7-145">Biblioteca de controles de Windows</span><span class="sxs-lookup"><span data-stu-id="1e0b7-145">Windows Control Library</span></span>|<span data-ttu-id="1e0b7-146">No</span><span class="sxs-lookup"><span data-stu-id="1e0b7-146">No</span></span>|
|<span data-ttu-id="1e0b7-147">Biblioteca de controles Web</span><span class="sxs-lookup"><span data-stu-id="1e0b7-147">Web Control Library</span></span>|<span data-ttu-id="1e0b7-148">No</span><span class="sxs-lookup"><span data-stu-id="1e0b7-148">No</span></span>|
|<span data-ttu-id="1e0b7-149">Servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="1e0b7-149">Windows Service</span></span>|<span data-ttu-id="1e0b7-150">No</span><span class="sxs-lookup"><span data-stu-id="1e0b7-150">No</span></span>|
|<span data-ttu-id="1e0b7-151">Sitio web</span><span class="sxs-lookup"><span data-stu-id="1e0b7-151">Web Site</span></span>|<span data-ttu-id="1e0b7-152">No</span><span class="sxs-lookup"><span data-stu-id="1e0b7-152">No</span></span>|

## <a name="see-also"></a><span data-ttu-id="1e0b7-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e0b7-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="1e0b7-154">Objects</span><span class="sxs-lookup"><span data-stu-id="1e0b7-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="1e0b7-155">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="1e0b7-156">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="1e0b7-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="1e0b7-157">Acceso ad los formularios de la aplicación</span><span class="sxs-lookup"><span data-stu-id="1e0b7-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
