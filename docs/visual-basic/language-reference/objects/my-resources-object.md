---
description: 'Más información acerca de: My. Resources (objeto)'
title: My.Resources (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: ecd8e79aacea85080dc341ae36b362a595893034
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640633"
---
# <a name="myresources-object"></a><span data-ttu-id="fad70-103">My.Resources (Objeto)</span><span class="sxs-lookup"><span data-stu-id="fad70-103">My.Resources Object</span></span>

<span data-ttu-id="fad70-104">Proporciona propiedades y clases para tener acceso a los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad70-104">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fad70-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fad70-105">Remarks</span></span>  

 <span data-ttu-id="fad70-106">El `My.Resources` objeto proporciona acceso a los recursos de la aplicación y permite recuperar dinámicamente los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad70-106">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="fad70-107">Para obtener más información, vea [administrar recursos de aplicación (.net)](/visualstudio/ide/managing-application-resources-dotnet).</span><span class="sxs-lookup"><span data-stu-id="fad70-107">For more information, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="fad70-108">El objeto `My.Resources` expone solo recursos globales.</span><span class="sxs-lookup"><span data-stu-id="fad70-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="fad70-109">No da acceso a los archivos de recursos asociados a los formularios.</span><span class="sxs-lookup"><span data-stu-id="fad70-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="fad70-110">Para acceder a los recursos de formulario, hay que hacerlo desde el formulario.</span><span class="sxs-lookup"><span data-stu-id="fad70-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="fad70-111">Puede tener acceso a los archivos de recursos específicos de la referencia cultural de la aplicación desde el `My.Resources` objeto.</span><span class="sxs-lookup"><span data-stu-id="fad70-111">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="fad70-112">De forma predeterminada, el `My.Resources` objeto busca recursos del archivo de recursos que coincida con la referencia cultural de la <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="fad70-112">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="fad70-113">Sin embargo, puede invalidar este comportamiento y especificar una referencia cultural determinada que se usará para los recursos.</span><span class="sxs-lookup"><span data-stu-id="fad70-113">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="fad70-114">Para obtener más información, vea [Recursos en aplicaciones .NET](../../../framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="fad70-114">For more information, see [Resources in Desktop Apps](../../../framework/resources/index.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fad70-115">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fad70-115">Properties</span></span>  

 <span data-ttu-id="fad70-116">Las propiedades del `My.Resources` objeto proporcionan acceso de solo lectura a los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad70-116">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="fad70-117">Para agregar o quitar recursos, use el **Diseñador de proyectos**.</span><span class="sxs-lookup"><span data-stu-id="fad70-117">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="fad70-118">Puede tener acceso a los recursos agregados a través del **Diseñador de proyectos** mediante `My.Resources.` *resourceName*.</span><span class="sxs-lookup"><span data-stu-id="fad70-118">You can access resources added through the **Project Designer** by using `My.Resources.`*resourceName*.</span></span>  
  
 <span data-ttu-id="fad70-119">También puede Agregar o quitar archivos de recursos seleccionando el proyecto en **Explorador de soluciones** y haciendo clic en **Agregar nuevo elemento** o **Agregar elemento existente** en el menú **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="fad70-119">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="fad70-120">Puede tener acceso a los recursos agregados de esta manera mediante `My.Resources.` *nombrearchivorecursos* `.` *resourceName*.</span><span class="sxs-lookup"><span data-stu-id="fad70-120">You can access resources added in this manner by using `My.Resources.`*resourceFileName*`.`*resourceName*.</span></span>  
  
 <span data-ttu-id="fad70-121">Cada recurso tiene un nombre, una categoría y un valor, y esta configuración de recursos determina el modo en que la propiedad para tener acceso al recurso aparece en el `My.Resources` objeto.</span><span class="sxs-lookup"><span data-stu-id="fad70-121">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="fad70-122">Para los recursos agregados en el **Diseñador de proyectos**:</span><span class="sxs-lookup"><span data-stu-id="fad70-122">For resources added in the **Project Designer**:</span></span>  
  
- <span data-ttu-id="fad70-123">El nombre determina el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fad70-123">The name determines the name of the property,</span></span>  
  
- <span data-ttu-id="fad70-124">Los datos del recurso son el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fad70-124">The resource data is the value of the property,</span></span>  
  
- <span data-ttu-id="fad70-125">La categoría determina el tipo de la propiedad:</span><span class="sxs-lookup"><span data-stu-id="fad70-125">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="fad70-126">Category</span><span class="sxs-lookup"><span data-stu-id="fad70-126">Category</span></span>|<span data-ttu-id="fad70-127">Tipo de datos de la propiedad</span><span class="sxs-lookup"><span data-stu-id="fad70-127">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="fad70-128">**Cadenas**</span><span class="sxs-lookup"><span data-stu-id="fad70-128">**Strings**</span></span>|[<span data-ttu-id="fad70-129">String</span><span class="sxs-lookup"><span data-stu-id="fad70-129">String</span></span>](../data-types/string-data-type.md)|  
|<span data-ttu-id="fad70-130">**Imágenes**</span><span class="sxs-lookup"><span data-stu-id="fad70-130">**Images**</span></span>|<xref:System.Drawing.Bitmap>|  
|<span data-ttu-id="fad70-131">**Iconos**</span><span class="sxs-lookup"><span data-stu-id="fad70-131">**Icons**</span></span>|<xref:System.Drawing.Icon>|  
|<span data-ttu-id="fad70-132">**Audio**</span><span class="sxs-lookup"><span data-stu-id="fad70-132">**Audio**</span></span>|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <span data-ttu-id="fad70-133">La <xref:System.IO.UnmanagedMemoryStream> clase se deriva de la <xref:System.IO.Stream> clase, por lo que se puede utilizar con métodos que toman secuencias, como el <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> método.</span><span class="sxs-lookup"><span data-stu-id="fad70-133">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="fad70-134">**Archivos**</span><span class="sxs-lookup"><span data-stu-id="fad70-134">**Files**</span></span>|<span data-ttu-id="fad70-135">-   [Cadena](../data-types/string-data-type.md) para los archivos de texto.</span><span class="sxs-lookup"><span data-stu-id="fad70-135">-   [String](../data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="fad70-136">-   <xref:System.Drawing.Bitmap> para los archivos de imagen.</span><span class="sxs-lookup"><span data-stu-id="fad70-136">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="fad70-137">-   <xref:System.Drawing.Icon> para los archivos de icono.</span><span class="sxs-lookup"><span data-stu-id="fad70-137">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="fad70-138">-   <xref:System.IO.UnmanagedMemoryStream> para archivos de sonido.</span><span class="sxs-lookup"><span data-stu-id="fad70-138">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="fad70-139">**Otros**</span><span class="sxs-lookup"><span data-stu-id="fad70-139">**Other**</span></span>|<span data-ttu-id="fad70-140">Lo determina la información de la columna de **tipo** del diseñador.</span><span class="sxs-lookup"><span data-stu-id="fad70-140">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="fad70-141">Clases</span><span class="sxs-lookup"><span data-stu-id="fad70-141">Classes</span></span>  

 <span data-ttu-id="fad70-142">El `My.Resources` objeto expone cada archivo de recursos como una clase con propiedades compartidas.</span><span class="sxs-lookup"><span data-stu-id="fad70-142">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="fad70-143">El nombre de clase es el mismo que el nombre del archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="fad70-143">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="fad70-144">Como se describe en la sección anterior, los recursos de un archivo de recursos se exponen como propiedades en la clase.</span><span class="sxs-lookup"><span data-stu-id="fad70-144">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fad70-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fad70-145">Example</span></span>  

 <span data-ttu-id="fad70-146">En este ejemplo se establece el título de un formulario en el recurso de cadena denominado `Form1Title` en el archivo de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad70-146">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="fad70-147">Para que el ejemplo funcione, la aplicación debe tener una cadena denominada `Form1Title` en su archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="fad70-147">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="fad70-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fad70-148">Example</span></span>  

 <span data-ttu-id="fad70-149">En este ejemplo se establece el icono del formulario en el icono denominado `Form1Icon` que está almacenado en el archivo de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad70-149">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="fad70-150">Para que el ejemplo funcione, la aplicación debe tener un icono denominado `Form1Icon` en su archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="fad70-150">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="fad70-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fad70-151">Example</span></span>  

 <span data-ttu-id="fad70-152">En este ejemplo se establece la imagen de fondo de un formulario en el recurso de imagen denominado `Form1Background` , que se encuentra en el archivo de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad70-152">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="fad70-153">Para que este ejemplo funcione, la aplicación debe tener un recurso de imagen denominado `Form1Background` en su archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="fad70-153">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="fad70-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fad70-154">Example</span></span>  

 <span data-ttu-id="fad70-155">En este ejemplo se reproduce el sonido que se almacena como un recurso de audio denominado `Form1Greeting` en el archivo de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad70-155">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="fad70-156">Para que el ejemplo funcione, la aplicación debe tener un recurso de audio denominado `Form1Greeting` en su archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="fad70-156">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="fad70-157">El `My.Computer.Audio.Play` método solo está disponible para aplicaciones Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fad70-157">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="fad70-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fad70-158">Example</span></span>  

 <span data-ttu-id="fad70-159">En este ejemplo se recupera la versión de la referencia cultural francesa de un recurso de cadena de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad70-159">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="fad70-160">El recurso se denomina `Message` .</span><span class="sxs-lookup"><span data-stu-id="fad70-160">The resource is named `Message`.</span></span> <span data-ttu-id="fad70-161">Para cambiar la referencia cultural que `My.Resources` utiliza el objeto, en el ejemplo se utiliza <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A> .</span><span class="sxs-lookup"><span data-stu-id="fad70-161">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="fad70-162">Para que este ejemplo funcione, la aplicación debe tener una cadena denominada `Message` en su archivo de recursos y la aplicación debe tener la versión de referencia cultural en francés de ese archivo de recursos, Resources.fr-fr. resx.</span><span class="sxs-lookup"><span data-stu-id="fad70-162">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="fad70-163">Si la aplicación no tiene la versión de referencia cultural en francés del archivo de recursos, el `My.Resource` objeto recupera el recurso del archivo de recursos de referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fad70-163">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="fad70-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="fad70-164">See also</span></span>

- [<span data-ttu-id="fad70-165">Administrar los recursos de la aplicación (.NET)</span><span class="sxs-lookup"><span data-stu-id="fad70-165">Managing Application Resources (.NET)</span></span>](/visualstudio/ide/managing-application-resources-dotnet)
- [<span data-ttu-id="fad70-166">Recursos de aplicaciones de escritorio</span><span class="sxs-lookup"><span data-stu-id="fad70-166">Resources in Desktop Apps</span></span>](../../../framework/resources/index.md)
