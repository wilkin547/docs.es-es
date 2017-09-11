---
title: Crear agentes de escucha de registro personalizados (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bc6fde8dcbb27157f3fd180ad393bb406222195e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a><span data-ttu-id="5c483-102">Tutorial: Crear agentes de escucha de registro personalizados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c483-102">Walkthrough: Creating Custom Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="5c483-103">En este tutorial se muestra cómo crear un agente de escucha de registro personalizado y configurarlo para escuchar la salida del objeto `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="5c483-103">This walkthrough demonstrates how to create a custom log listener and configure it to listen to the output of the `My.Application.Log` object.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="5c483-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="5c483-104">Getting Started</span></span>  
 <span data-ttu-id="5c483-105">Los agentes de escucha de registro deben heredar de la clase <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="5c483-105">Log listeners must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
#### <a name="to-create-the-listener"></a><span data-ttu-id="5c483-106">Para crear el agente de escucha</span><span class="sxs-lookup"><span data-stu-id="5c483-106">To create the listener</span></span>  
  
-   <span data-ttu-id="5c483-107">En la aplicación, cree una clase denominada `SimpleListener` que herede de <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="5c483-107">In your application, create a class named `SimpleListener` that inherits from <xref:System.Diagnostics.TraceListener>.</span></span>  
  
     <span data-ttu-id="5c483-108">[!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5c483-108">[!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]</span></span>  
  
     <span data-ttu-id="5c483-109">Los métodos <xref:System.Diagnostics.TraceListener.Write%2A> y <xref:System.Diagnostics.TraceListener.WriteLine%2A>, requeridos por la clase base, llame a `MsgBox` para mostrar su entrada.</span><span class="sxs-lookup"><span data-stu-id="5c483-109">The <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods, required by the base class, call `MsgBox` to display their input.</span></span>  
  
     <span data-ttu-id="5c483-110">El atributo <xref:System.Security.Permissions.HostProtectionAttribute> se aplica a los métodos <xref:System.Diagnostics.TraceListener.Write%2A> y <xref:System.Diagnostics.TraceListener.WriteLine%2A>, para que sus atributos coincidan con los métodos de clase base.</span><span class="sxs-lookup"><span data-stu-id="5c483-110">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is applied to the <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods so that their attributes match the base class methods.</span></span> <span data-ttu-id="5c483-111">El atributo <xref:System.Security.Permissions.HostProtectionAttribute> permite al host que ejecuta el código determinar que el código expone sincronización de protección de host.</span><span class="sxs-lookup"><span data-stu-id="5c483-111">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute allows the host that runs the code to determine that the code exposes host-protection synchronization.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c483-112">El atributo <xref:System.Security.Permissions.HostProtectionAttribute> solo es eficaz en aplicaciones no administradas que hospedan Common Language Runtime e implementan protección de host, como SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5c483-112">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is effective only on unmanaged applications that host the common language runtime and that implement host protection, such as SQL Server.</span></span>  
  
 <span data-ttu-id="5c483-113">Para asegurarse de que `My.Application.Log` usa su agente de escucha de registro, debe asignar un nombre seguro al ensamblado que contiene el agente de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="5c483-113">To ensure that `My.Application.Log` uses your log listener, you should strongly name the assembly that contains your log listener.</span></span>  
  
 <span data-ttu-id="5c483-114">En el procedimiento siguiente se proporcionan algunos pasos sencillos para crear un ensamblado de agente de escucha de registro con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="5c483-114">The next procedure provides some simple steps for creating a strongly named log-listener assembly.</span></span> <span data-ttu-id="5c483-115">Para obtener más información, vea [Crear y utilizar ensamblados con nombre seguro](https://msdn.microsoft.com/library/xwb8f617).</span><span class="sxs-lookup"><span data-stu-id="5c483-115">For more information, see [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617).</span></span>  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a><span data-ttu-id="5c483-116">Para asignar un nombre seguro al ensamblado de agente de escucha de registro</span><span class="sxs-lookup"><span data-stu-id="5c483-116">To strongly name the log-listener assembly</span></span>  
  
1.  <span data-ttu-id="5c483-117">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="5c483-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5c483-118">En el menú **Proyecto** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5c483-118">On the **Project** menu, choose **Properties**.</span></span> <span data-ttu-id="5c483-119">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="5c483-119">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="5c483-120">Haga clic en la pestaña **Firma**.</span><span class="sxs-lookup"><span data-stu-id="5c483-120">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="5c483-121">Active la casilla **Firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="5c483-121">Select the **Sign the assembly** box.</span></span>  
  
4.  <span data-ttu-id="5c483-122">Seleccione **\<Nuevo>** en la lista desplegable **Elija un archivo de clave de nombre seguro**.</span><span class="sxs-lookup"><span data-stu-id="5c483-122">Select **\<New>** from the **Choose a strong name key file** drop-down list.</span></span>  
  
     <span data-ttu-id="5c483-123">Se abre el cuadro de diálogo **Crear clave de nombre seguro**.</span><span class="sxs-lookup"><span data-stu-id="5c483-123">The **Create Strong Name Key** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="5c483-124">Especifique un nombre para el archivo de clave en el cuadro **Nombre del archivo de clave**.</span><span class="sxs-lookup"><span data-stu-id="5c483-124">Provide a name for the key file in the **Key file name** box.</span></span>  
  
6.  <span data-ttu-id="5c483-125">Escriba una contraseña en los cuadros **Escribir contraseña** y **Confirmar contraseña**.</span><span class="sxs-lookup"><span data-stu-id="5c483-125">Enter a password in the **Enter password** and **Confirm password** boxes.</span></span>  
  
7.  <span data-ttu-id="5c483-126">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c483-126">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="5c483-127">Vuelva a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c483-127">Rebuild the application.</span></span>  
  
## <a name="adding-the-listener"></a><span data-ttu-id="5c483-128">Agregar el agente de escucha</span><span class="sxs-lookup"><span data-stu-id="5c483-128">Adding the Listener</span></span>  
 <span data-ttu-id="5c483-129">Ahora que el ensamblado tiene un nombre seguro, debe determinar el nombre seguro del agente de escucha para que `My.Application.Log` use el agente de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="5c483-129">Now that the assembly has a strong name, you need to determine the strong name of the listener so that `My.Application.Log` uses your log listener.</span></span>  
  
 <span data-ttu-id="5c483-130">El formato de un tipo con nombre seguro es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c483-130">The format of a strongly named type is as follows.</span></span>  
  
 <span data-ttu-id="5c483-131">\<nombre de tipo>, \<nombre de ensamblado>, \<número de versión>, \<referencia cultural>, \<nombre seguro></span><span class="sxs-lookup"><span data-stu-id="5c483-131">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span></span>  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a><span data-ttu-id="5c483-132">Para determinar el nombre seguro del agente de escucha</span><span class="sxs-lookup"><span data-stu-id="5c483-132">To determine the strong name of the listener</span></span>  
  
-   <span data-ttu-id="5c483-133">En el código siguiente se muestra cómo determinar el nombre de tipo seguro para `SimpleListener`.</span><span class="sxs-lookup"><span data-stu-id="5c483-133">The following code shows how to determine the strongly named type name for `SimpleListener`.</span></span>  
  
     <span data-ttu-id="5c483-134">[!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5c483-134">[!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]</span></span>  
  
     <span data-ttu-id="5c483-135">El nombre seguro del tipo depende de su proyecto.</span><span class="sxs-lookup"><span data-stu-id="5c483-135">The strong name of the type depends on your project.</span></span>  
  
 <span data-ttu-id="5c483-136">Con el nombre seguro, puede agregar el agente de escucha a la colección de agente de escucha de registro de `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="5c483-136">With the strong name, you can add the listener to the `My.Application.Log` log-listener collection.</span></span>  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a><span data-ttu-id="5c483-137">Para agregar el agente de escucha a My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="5c483-137">To add the listener to My.Application.Log</span></span>  
  
1.  <span data-ttu-id="5c483-138">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5c483-138">Right-click on app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="5c483-139">O bien</span><span class="sxs-lookup"><span data-stu-id="5c483-139">-or-</span></span>  
  
     <span data-ttu-id="5c483-140">Si hay un archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="5c483-140">If there is an app.config file:</span></span>  
  
    1.  <span data-ttu-id="5c483-141">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="5c483-141">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="5c483-142">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="5c483-142">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="5c483-143">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5c483-143">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="5c483-144">Busque la sección `<listeners>` , en la sección `<source>` con el atributo `name` el "DefaultSource", ubicada en la sección `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="5c483-144">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="5c483-145">La sección `<sources>` se encuentra en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="5c483-145">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="5c483-146">Agregue este elemento a la sección `<listeners>`:</span><span class="sxs-lookup"><span data-stu-id="5c483-146">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" />  
    ```  
  
4.  <span data-ttu-id="5c483-147">Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="5c483-147">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="5c483-148">Agregue este elemento a dicha sección `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="5c483-148">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     <span data-ttu-id="5c483-149">Cambie el valor de `SimpleLogStrongName` para que sea el nombre seguro del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="5c483-149">Change the value of `SimpleLogStrongName` to be the strong name of the listener.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c483-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c483-150">See Also</span></span>  
 <span data-ttu-id="5c483-151"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5c483-151"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="5c483-152">[Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="5c483-152">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="5c483-153">[Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="5c483-153">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 <span data-ttu-id="5c483-154">[Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="5c483-154">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 [<span data-ttu-id="5c483-155">Tutorial: Cambiar el lugar donde My.Application.Log escribe información</span><span class="sxs-lookup"><span data-stu-id="5c483-155">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

