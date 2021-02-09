---
description: 'Más información acerca de: Tutorial: Crear agentes de escucha de registro personalizados (Visual Basic)'
title: Crear agentes de escucha de registro personalizados
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: bc5e1743eeaec427adf909ca95aa1979ce61a993
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792302"
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a><span data-ttu-id="25677-103">Tutorial: Crear agentes de escucha de registro personalizados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25677-103">Walkthrough: Creating Custom Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="25677-104">En este tutorial se muestra cómo crear un agente de escucha de registro personalizado y configurarlo para escuchar la salida del objeto `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="25677-104">This walkthrough demonstrates how to create a custom log listener and configure it to listen to the output of the `My.Application.Log` object.</span></span>

## <a name="getting-started"></a><span data-ttu-id="25677-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="25677-105">Getting Started</span></span>

<span data-ttu-id="25677-106">Los agentes de escucha de registro deben heredar de la clase <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="25677-106">Log listeners must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span>

#### <a name="to-create-the-listener"></a><span data-ttu-id="25677-107">Para crear el agente de escucha</span><span class="sxs-lookup"><span data-stu-id="25677-107">To create the listener</span></span>

- <span data-ttu-id="25677-108">En la aplicación, cree una clase denominada `SimpleListener` que herede de <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="25677-108">In your application, create a class named `SimpleListener` that inherits from <xref:System.Diagnostics.TraceListener>.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#16)]

     <span data-ttu-id="25677-109">Los métodos <xref:System.Diagnostics.TraceListener.Write%2A> y <xref:System.Diagnostics.TraceListener.WriteLine%2A>, requeridos por la clase base, llame a `MsgBox` para mostrar su entrada.</span><span class="sxs-lookup"><span data-stu-id="25677-109">The <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods, required by the base class, call `MsgBox` to display their input.</span></span>

     <span data-ttu-id="25677-110">El atributo <xref:System.Security.Permissions.HostProtectionAttribute> se aplica a los métodos <xref:System.Diagnostics.TraceListener.Write%2A> y <xref:System.Diagnostics.TraceListener.WriteLine%2A>, para que sus atributos coincidan con los métodos de clase base.</span><span class="sxs-lookup"><span data-stu-id="25677-110">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is applied to the <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods so that their attributes match the base class methods.</span></span> <span data-ttu-id="25677-111">El atributo <xref:System.Security.Permissions.HostProtectionAttribute> permite al host que ejecuta el código determinar que el código expone sincronización de protección de host.</span><span class="sxs-lookup"><span data-stu-id="25677-111">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute allows the host that runs the code to determine that the code exposes host-protection synchronization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25677-112">El atributo <xref:System.Security.Permissions.HostProtectionAttribute> solo es eficaz en aplicaciones no administradas que hospedan Common Language Runtime e implementan protección de host, como SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25677-112">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is effective only on unmanaged applications that host the common language runtime and that implement host protection, such as SQL Server.</span></span>

<span data-ttu-id="25677-113">Para asegurarse de que `My.Application.Log` usa su agente de escucha de registro, debe asignar un nombre seguro al ensamblado que contiene el agente de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="25677-113">To ensure that `My.Application.Log` uses your log listener, you should strongly name the assembly that contains your log listener.</span></span>

<span data-ttu-id="25677-114">En el procedimiento siguiente se proporcionan algunos pasos sencillos para crear un ensamblado de agente de escucha de registro con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="25677-114">The next procedure provides some simple steps for creating a strongly named log-listener assembly.</span></span> <span data-ttu-id="25677-115">Para obtener más información, vea [Crear y utilizar ensamblados con nombre seguro](../../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="25677-115">For more information, see [Creating and Using Strong-Named Assemblies](../../../../standard/assembly/create-use-strong-named.md).</span></span>

#### <a name="to-strongly-name-the-log-listener-assembly"></a><span data-ttu-id="25677-116">Para asignar un nombre seguro al ensamblado de agente de escucha de registro</span><span class="sxs-lookup"><span data-stu-id="25677-116">To strongly name the log-listener assembly</span></span>

1. <span data-ttu-id="25677-117">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="25677-117">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="25677-118">En el menú **Proyecto** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="25677-118">On the **Project** menu, choose **Properties**.</span></span>

2. <span data-ttu-id="25677-119">Haga clic en la pestaña **Firma**.</span><span class="sxs-lookup"><span data-stu-id="25677-119">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="25677-120">Active la casilla **Firmar el ensamblado** .</span><span class="sxs-lookup"><span data-stu-id="25677-120">Select the **Sign the assembly** box.</span></span>

4. <span data-ttu-id="25677-121">Seleccione **\<New>** en la lista desplegable **Elija un archivo de clave de nombre seguro**.</span><span class="sxs-lookup"><span data-stu-id="25677-121">Select **\<New>** from the **Choose a strong name key file** drop-down list.</span></span>

     <span data-ttu-id="25677-122">Se abre el cuadro de diálogo **Crear clave de nombre seguro**.</span><span class="sxs-lookup"><span data-stu-id="25677-122">The **Create Strong Name Key** dialog box opens.</span></span>

5. <span data-ttu-id="25677-123">Especifique un nombre para el archivo de clave en el cuadro **Nombre del archivo de clave**.</span><span class="sxs-lookup"><span data-stu-id="25677-123">Provide a name for the key file in the **Key file name** box.</span></span>

6. <span data-ttu-id="25677-124">Escriba una contraseña en los cuadros **Escribir contraseña** y **Confirmar contraseña**.</span><span class="sxs-lookup"><span data-stu-id="25677-124">Enter a password in the **Enter password** and **Confirm password** boxes.</span></span>

7. <span data-ttu-id="25677-125">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25677-125">Click **OK**.</span></span>

8. <span data-ttu-id="25677-126">Vuelva a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="25677-126">Rebuild the application.</span></span>

## <a name="adding-the-listener"></a><span data-ttu-id="25677-127">Agregar el agente de escucha</span><span class="sxs-lookup"><span data-stu-id="25677-127">Adding the Listener</span></span>

<span data-ttu-id="25677-128">Ahora que el ensamblado tiene un nombre seguro, debe determinar el nombre seguro del agente de escucha para que `My.Application.Log` use el agente de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="25677-128">Now that the assembly has a strong name, you need to determine the strong name of the listener so that `My.Application.Log` uses your log listener.</span></span>

<span data-ttu-id="25677-129">El formato de un tipo con nombre seguro es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="25677-129">The format of a strongly named type is as follows.</span></span>

<span data-ttu-id="25677-130">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span><span class="sxs-lookup"><span data-stu-id="25677-130">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span></span>

#### <a name="to-determine-the-strong-name-of-the-listener"></a><span data-ttu-id="25677-131">Para determinar el nombre seguro del agente de escucha</span><span class="sxs-lookup"><span data-stu-id="25677-131">To determine the strong name of the listener</span></span>

- <span data-ttu-id="25677-132">En el código siguiente se muestra cómo determinar el nombre de tipo seguro para `SimpleListener`.</span><span class="sxs-lookup"><span data-stu-id="25677-132">The following code shows how to determine the strongly named type name for `SimpleListener`.</span></span>

     [!code-vb[VbVbalrMyApplicationLog#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#17)]

     <span data-ttu-id="25677-133">El nombre seguro del tipo depende de su proyecto.</span><span class="sxs-lookup"><span data-stu-id="25677-133">The strong name of the type depends on your project.</span></span>

<span data-ttu-id="25677-134">Con el nombre seguro, puede agregar el agente de escucha a la colección de agente de escucha de registro de `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="25677-134">With the strong name, you can add the listener to the `My.Application.Log` log-listener collection.</span></span>

#### <a name="to-add-the-listener-to-myapplicationlog"></a><span data-ttu-id="25677-135">Para agregar el agente de escucha a My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="25677-135">To add the listener to My.Application.Log</span></span>

1. <span data-ttu-id="25677-136">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="25677-136">Right-click on app.config in the **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="25677-137">o bien</span><span class="sxs-lookup"><span data-stu-id="25677-137">-or-</span></span>

     <span data-ttu-id="25677-138">Si hay un archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="25677-138">If there is an app.config file:</span></span>

    1. <span data-ttu-id="25677-139">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="25677-139">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="25677-140">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="25677-140">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="25677-141">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="25677-141">Click **Add**.</span></span>

2. <span data-ttu-id="25677-142">Busque la sección `<listeners>` , en la sección `<source>` con el atributo `name` el "DefaultSource", ubicada en la sección `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="25677-142">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="25677-143">La sección `<sources>` se encuentra en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="25677-143">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="25677-144">Agregue este elemento a la sección `<listeners>`:</span><span class="sxs-lookup"><span data-stu-id="25677-144">Add this element to the `<listeners>` section:</span></span>

    ```xml
    <add name="SimpleLog" />
    ```

4. <span data-ttu-id="25677-145">Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="25677-145">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="25677-146">Agregue este elemento a dicha sección `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="25677-146">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="SimpleLog" type="SimpleLogStrongName" />
    ```

     <span data-ttu-id="25677-147">Cambie el valor de `SimpleLogStrongName` para que sea el nombre seguro del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="25677-147">Change the value of `SimpleLogStrongName` to be the strong name of the listener.</span></span>

## <a name="see-also"></a><span data-ttu-id="25677-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="25677-148">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="25677-149">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="25677-149">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="25677-150">Cómo: Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="25677-150">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="25677-151">Cómo: Escribir mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="25677-151">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)
- [<span data-ttu-id="25677-152">Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="25677-152">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
