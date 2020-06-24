---
title: Herramienta del editor de configuración (SvcConfigEditor.exe)
description: Obtenga información sobre cómo administrar la configuración de enlaces, comportamientos, servicios y diagnósticos de WCF mediante el editor de configuración de servicio de WCF.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: 258437ff616b969d40feabbfff364ad2cc6b25bc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247654"
---
# <a name="configuration-editor-tool-svcconfigeditorexe"></a><span data-ttu-id="8ddd8-103">Herramienta del editor de configuración (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="8ddd8-103">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>

<span data-ttu-id="8ddd8-104">El editor de configuración de servicios de Windows Communication Foundation (SvcConfigEditor.exe) permite a los administradores y programadores crear y modificar la configuración para los servicios WCF mediante una interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-104">The Windows Communication Foundation (WCF) Service Configuration Editor (SvcConfigEditor.exe) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="8ddd8-105">Con esta herramienta puede administrar los valores para los enlaces, comportamientos, servicios y diagnósticos de WCF sin tener que editar directamente los archivos de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-105">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without having to directly edit XML configuration files.</span></span>

<span data-ttu-id="8ddd8-106">El Editor de configuración de servicio se puede encontrar en la carpeta C:\Archivos de programa\Microsoft SDKs\Windows\v6.0\Bin.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-106">Service Configuration Editor can be found in the C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin folder.</span></span>

## <a name="the-wcf-configuration-editor"></a><span data-ttu-id="8ddd8-107">El editor de configuración de WCF</span><span class="sxs-lookup"><span data-stu-id="8ddd8-107">The WCF Configuration Editor</span></span>

<span data-ttu-id="8ddd8-108">El editor de configuración de servicio viene con un asistente que lo guía a través de todos los pasos para configurar un servicio o cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-108">Service Configuration Editor comes with a wizard that guides you through all the steps in configuring a WCF service or client.</span></span> <span data-ttu-id="8ddd8-109">Se le aconseja encarecidamente que utilice directamente el asistente en lugar del editor.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-109">You are strongly advised to use the wizard instead of the editor directly.</span></span>

<span data-ttu-id="8ddd8-110">Si ya tiene algunos archivos de configuración que obedecen al esquema estándar de System.Configuration, puede administrar valores concretos para enlaces, comportamiento, servicios y diagnósticos mediante la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-110">If you already have some configuration files that comply with the standard System.Configuration schema, you can manage specific settings for bindings, behavior, services, and diagnostics with the user interface.</span></span> <span data-ttu-id="8ddd8-111">El editor de configuración de servicio le permite administrar los valores para los archivos de configuración de WCF existentes, así como archivos ejecutables, servicios de COM+ y servicios hospedados en web.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-111">The Service Configuration Editor enables you to manage the settings for existing WCF configuration files as well as executable files, COM+ services, and Web-hosted services.</span></span> <span data-ttu-id="8ddd8-112">Cuando se abre un servicio hospedado en web con el Editor de configuración de servicios, se muestran las secciones de configuraciones heredadas de los nodos de nivel superior y la propia configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-112">When opening a Web-hosted service with Service Configuration Editor, both the service’s own configuration and inherited configurations sections of upper level nodes are shown.</span></span>

<span data-ttu-id="8ddd8-113">Dado que la configuración de WCF se encuentra en la sección `<system.serviceModel>` del archivo de configuración, el editor actúa exclusivamente sobre el contenido de este elemento y no accede a otros elementos del mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-113">Because WCF configuration settings are located in the `<system.serviceModel>` section of the configuration file, the editor operates exclusively on the content of this element and does not access other elements in the same file.</span></span> <span data-ttu-id="8ddd8-114">Puede navegar directamente a archivos de configuración existentes o puede seleccionar un ensamblado que contenga un servicio, un directorio virtual o un servicio de COM+.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-114">You can navigate to existing configuration files directly or you can select an assembly that contains a service, virtual directory, or COM+ service.</span></span> <span data-ttu-id="8ddd8-115">El editor carga el archivo de configuración para ese servicio particular y permite que el usuario agregue elementos nuevos o modifique elementos existentes anidados en la sección `<system.serviceModel>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-115">The editor loads the configuration file for that particular service and allows the user to either add new elements or edit existing elements nested in the `<system.serviceModel>` section of the configuration file.</span></span>

<span data-ttu-id="8ddd8-116">El editor admite IntelliSense y exige la compatibilidad del esquema.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-116">The editor supports IntelliSense and enforces schema compliance.</span></span> <span data-ttu-id="8ddd8-117">Se garantiza que el resultado obtenido es compatible con el esquema del archivo de configuración y tiene valores de datos sintácticamente correctos.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-117">The resulting output is guaranteed to comply with the schema of the configuration file and to have syntactically correct data values.</span></span> <span data-ttu-id="8ddd8-118">Sin embargo, el editor no garantiza que el archivo de configuración sea semánticamente válido.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-118">However, the editor does not guarantee that the configuration file is semantically valid.</span></span> <span data-ttu-id="8ddd8-119">En otras palabras, el editor no garantiza que el archivo de configuración pueda funcionar con el servicio que configura.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-119">In other words, the editor does not guarantee that the configuration file can work with the service it configures.</span></span>

> [!CAUTION]
> <span data-ttu-id="8ddd8-120">El editor no puede purgar un elemento de configuración a partir del archivo de configuración cuando ha modificado el elemento.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-120">The editor cannot purge a configuration element from the configuration file once you have modified the element.</span></span> <span data-ttu-id="8ddd8-121">Por ejemplo, si utiliza el editor para establecer el nombre de punto de conexión en una cadena que no esté vacía y guardarlo, el archivo de configuración tendrá el contenido del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-121">For example, if you use the editor to set the endpoint name to a non-empty string and save it, the configuration file has the following content, as shown in the following example.</span></span>
>
> `<endpoint binding="basicHttpBinding" name="somename" />`
>
> <span data-ttu-id="8ddd8-122">Si intenta quitar el nombre estableciéndolo en una cadena vacía y guardar el archivo, el archivo de configuración todavía contendrá el atributo `name`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-122">If you attempt to remove the name by setting it to an empty string and save the file, the configuration file still contains the `name` attribute, as shown in the following example.</span></span>
>
> `<endpoint binding="basicHttpBinding" name="" />`
>
> <span data-ttu-id="8ddd8-123">Para purgar el atributo, debe modificar manualmente el elemento mediante otro editor de texto.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-123">To purge the attribute, you must manually edit the element using another text editor.</span></span>
>
> <span data-ttu-id="8ddd8-124">Debería tener mucho cuidado con este problema al utilizar el elemento `issueToken` del comportamiento de extremo `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-124">You should be especially careful with this issue when you use the `issueToken` element of the `clientCredential` Endpoint behavior.</span></span> <span data-ttu-id="8ddd8-125">Específicamente, el atributo `address` de su subelemento `localIssuer` no debe ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-125">Specifically, the `address` attribute of its `localIssuer` sub-element must not be an empty string.</span></span> <span data-ttu-id="8ddd8-126">Si ha modificado el atributo `address` mediante el editor de configuración y desea quitarlo completamente, debería hacerlo utilizando una herramienta diferente del editor.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-126">If you have modified the `address` attribute using the Configuration Editor and want to remove it completely, you should do so using a tool other than the Editor.</span></span> <span data-ttu-id="8ddd8-127">De lo contrario, el atributo contiene una cadena vacía y su aplicación inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-127">Otherwise, the attribute contains an empty string and your application throws an exception.</span></span>

## <a name="using-the-configuration-editor"></a><span data-ttu-id="8ddd8-128">Utilización del editor de configuración</span><span class="sxs-lookup"><span data-stu-id="8ddd8-128">Using the Configuration Editor</span></span>

<span data-ttu-id="8ddd8-129">El Editor de configuración de servicio se puede encontrar en la siguiente ubicación de instalación de Windows SDK:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-129">The Service Configuration Editor can be found at the following Windows SDK installation location:</span></span>

<span data-ttu-id="8ddd8-130">C:\Archivos de Programa\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="8ddd8-130">C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe</span></span>

<span data-ttu-id="8ddd8-131">Después de iniciar el editor de configuración de servicio, puede usar el menú **archivo/abrir** para buscar el servicio o ensamblado que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-131">After you launch the Service Configuration Editor, you can use the **File/Open** menu to browse for the service or assembly you want to manage.</span></span> <span data-ttu-id="8ddd8-132">Puede abrir directamente los archivos de configuración, busque WCF/servicios COM + y abra los archivos de configuración para servicios hospedados en web.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-132">You can open configuration files directly, browse for WCF /COM+ services, and open configuration files for Web-hosted services.</span></span>

<span data-ttu-id="8ddd8-133">La interfaz de usuario del editor de configuración de servicio está dividida en las áreas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-133">The Service Configuration Editor's user interface is divided into the following areas:</span></span>

- <span data-ttu-id="8ddd8-134">Panel Ver árbol, que muestra los elementos de configuración en una estructura de árbol a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-134">Tree View Pane, which displays configuration elements in a tree structure on the left.</span></span> <span data-ttu-id="8ddd8-135">Puede realizar operaciones en el árbol haciendo clic con el botón secundario en los nodos.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-135">You can perform operations in the tree by right-clicking the nodes.</span></span>

- <span data-ttu-id="8ddd8-136">Panel de tareas, que muestra las tareas comunes para los elementos vigentes en la parte inferior izquierda de la ventana.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-136">Task Pane, which displays common tasks for current elements on the lower-left of the window</span></span>

- <span data-ttu-id="8ddd8-137">Panel de detalles, que muestra valores detallados del nodo de configuración seleccionado en Ver árbol a la derecha.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-137">Detail Pane, which displays detailed settings of the configuration node selected in the Tree View on the right.</span></span>

### <a name="opening-a-configuration-file"></a><span data-ttu-id="8ddd8-138">Abrir un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8ddd8-138">Opening a Configuration File</span></span>

1. <span data-ttu-id="8ddd8-139">Inicie el editor de configuración de servicio mediante una ventana de comandos para navegar a la ubicación de instalación de WCF y, a continuación, escriba `SvcConfigEditor.exe` .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-139">Start Service Configuration Editor by using a command window to navigate to your WCF installation location, and then type `SvcConfigEditor.exe`.</span></span>

2. <span data-ttu-id="8ddd8-140">En el menú **archivo** , seleccione **abrir** y haga clic en el tipo de archivo que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-140">From the **File** menu, select **Open** and click the type of file you want to manage.</span></span>

3. <span data-ttu-id="8ddd8-141">En el cuadro de diálogo **abrir** , navegue hasta el archivo específico que desea administrar y haga doble clic en él.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-141">In the **Open** dialog box, navigate to the specific file you want to manage and double-click it.</span></span>

<span data-ttu-id="8ddd8-142">El visor sigue automáticamente la ruta de acceso de fusión mediante combinación de configuración y crea una vista de la configuración combinada.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-142">The viewer automatically follows the configuration merge path and creates a view of the merged configuration.</span></span> <span data-ttu-id="8ddd8-143">Por ejemplo, la configuración real de un servicio no hospedado es una combinación de Machine.config y App.config. Cualquier cambio se aplica al archivo activo en SvcConfigEditor.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-143">For example, the actual configuration of a non-hosted service is a combination of Machine.config and App.config. Any changes are applied to the active file in the SvcConfigEditor.</span></span> <span data-ttu-id="8ddd8-144">Si desea modificar un archivo concreto en la ruta de acceso de fusión mediante combinación de configuración, debería abrirlo directamente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-144">If you want to edit a specific file in the configuration merge path, you should open it directly.</span></span>

> [!NOTE]
> <span data-ttu-id="8ddd8-145">El editor de configuración recarga el archivo de configuración abierto actualmente cuando éste se ha modificado fuera del editor.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-145">Configuration Editor reloads the currently opened configuration file when the latter has been modified outside the Editor.</span></span> <span data-ttu-id="8ddd8-146">Cuando esto pasa, se pierden todos los cambios que no están guardados dentro del Editor de forma duradera.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-146">When this happens, all the changes that are not durably saved inside the Editor are lost.</span></span> <span data-ttu-id="8ddd8-147">Si la recarga sucede constantemente, la causa más probable es un servicio que tiene acceso al archivo de configuración continuamente, por ejemplo un software antivirus que se ejecuta en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-147">If reloading happens consistently, the most likely cause is a service that constantly accesses the configuration file, for example, an antivirus software running in the background.</span></span> <span data-ttu-id="8ddd8-148">Para resolver esto, asegúrese de que el editor de configuración es el único proceso que puede tener acceso al archivo cuando se abre.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-148">To resolve this, ensure that Configuration Editor is the only process that can access the file when it is opened.</span></span>

### <a name="services"></a><span data-ttu-id="8ddd8-149">Servicios</span><span class="sxs-lookup"><span data-stu-id="8ddd8-149">Services</span></span>

<span data-ttu-id="8ddd8-150">El nodo **servicios** muestra todos los servicios asignados actualmente en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-150">The **Services** node displays all of the services currently assigned in the configuration file.</span></span> <span data-ttu-id="8ddd8-151">Cada subnodo del árbol corresponde a un subelemento del `services` elemento <> del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-151">Each sub-node in the tree corresponds to a sub-element of the <`services`> element in the configuration file.</span></span>

<span data-ttu-id="8ddd8-152">Al hacer clic en el nodo **servicios** , puede ver o realizar tareas en la página Resumen del servicio en el panel de **detalles** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-152">When you click the **Services** node, you can view or perform tasks on the service Summary Page in the **Detail** Pane.</span></span>

#### <a name="creating-a-new-service-configuration"></a><span data-ttu-id="8ddd8-153">Crear una nueva configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="8ddd8-153">Creating a new Service Configuration</span></span>

<span data-ttu-id="8ddd8-154">Puede crear una nueva configuración de servicio de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-154">You can create a new service configuration in the following ways:</span></span>

- <span data-ttu-id="8ddd8-155">Mediante un asistente: haga clic en el vínculo **crear un nuevo servicio...**</span><span class="sxs-lookup"><span data-stu-id="8ddd8-155">Using a Wizard: Click the link **Create a New Service…**</span></span> <span data-ttu-id="8ddd8-156">en el panel de tareas o en la página de resumen para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-156">on the Task Pane or Summary Page to launch the wizard.</span></span> <span data-ttu-id="8ddd8-157">También puede hacerlo en el menú **archivo** -> **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-157">You can also do so in the **File** menu -> **Add New Item**.</span></span>

- <span data-ttu-id="8ddd8-158">Crear manualmente: puede hacer clic con el botón secundario en el nodo **servicios** y elegir **nuevo servicio**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-158">Create manually: You can right-click the **Services** node and choose **New Service**.</span></span>

#### <a name="creating-a-new-service-endpoint-configuration"></a><span data-ttu-id="8ddd8-159">Crear una nueva configuración de extremo de servicio</span><span class="sxs-lookup"><span data-stu-id="8ddd8-159">Creating a new Service Endpoint Configuration</span></span>

<span data-ttu-id="8ddd8-160">Puede crear una nueva configuración de punto de conexión de servicio de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-160">You can create a new service endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="8ddd8-161">Crear mediante un asistente: haga clic en el vínculo **crear un nuevo punto de conexión de servicio..** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-161">Create using a Wizard: click the link **Create a New Service Endpoint…**</span></span> <span data-ttu-id="8ddd8-162">en el panel de tareas o en la página de resumen para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-162">on the Task Pane or Summary Page to launch the wizard.</span></span> <span data-ttu-id="8ddd8-163">También puede hacerlo en el menú **archivo** -> **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-163">You can also do so in the **File** menu -> **Add New Item**.</span></span>

- <span data-ttu-id="8ddd8-164">Crear manualmente: una vez creado un servicio, puede hacer clic con el botón secundario en el nodo **extremos** y elegir "**nuevo punto de conexión de servicio**".</span><span class="sxs-lookup"><span data-stu-id="8ddd8-164">Create manually: Once you created a Service, you can right-click the **Endpoints** node and choose "**New Service Endpoint**".</span></span>

#### <a name="editing-a-service-configuration"></a><span data-ttu-id="8ddd8-165">Editar una configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="8ddd8-165">Editing a Service Configuration</span></span>

1. <span data-ttu-id="8ddd8-166">Haga clic en un nodo de **servicio** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-166">Click a **Service** node.</span></span>

2. <span data-ttu-id="8ddd8-167">Edite la configuración en la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-167">Edit the settings in the property grids.</span></span>

#### <a name="editing-a-service-endpoint-configuration"></a><span data-ttu-id="8ddd8-168">Editar una configuración de punto de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="8ddd8-168">Editing a Service Endpoint Configuration</span></span>

1. <span data-ttu-id="8ddd8-169">Haga clic en un nodo de **punto de conexión de servicio** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-169">Click a **Service Endpoint** node.</span></span>

2. <span data-ttu-id="8ddd8-170">Edite la configuración en la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-170">Edit the settings in the property grids.</span></span>

#### <a name="adding-a-base-address"></a><span data-ttu-id="8ddd8-171">Agregar una dirección base</span><span class="sxs-lookup"><span data-stu-id="8ddd8-171">Adding a Base Address</span></span>

1. <span data-ttu-id="8ddd8-172">Haga clic en el nodo **host** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-172">Click the **Host** node.</span></span>

2. <span data-ttu-id="8ddd8-173">Haga clic en el botón **Nuevo...**</span><span class="sxs-lookup"><span data-stu-id="8ddd8-173">Click the **New…**</span></span> <span data-ttu-id="8ddd8-174">en la sección **direcciones base** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-174">button in the **Base Addresses** section.</span></span>

3. <span data-ttu-id="8ddd8-175">Escriba el URI de la dirección base en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-175">Type in the base address URI in the dialog box.</span></span>

4. <span data-ttu-id="8ddd8-176">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-176">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="8ddd8-177">No se puede editar el valor de [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) dentro de esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-177">You cannot edit the value of [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) inside this tool.</span></span> <span data-ttu-id="8ddd8-178">Para agregar o modificar este elemento, debe utilizar un editor de texto o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-178">To add or modify this element, you should use a text editor or Visual Studio.</span></span>

### <a name="client"></a><span data-ttu-id="8ddd8-179">Cliente</span><span class="sxs-lookup"><span data-stu-id="8ddd8-179">Client</span></span>

<span data-ttu-id="8ddd8-180">El nodo **cliente** muestra todos los puntos de conexión de cliente en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-180">The **Client** node displays all of the client endpoints in the configuration file.</span></span> <span data-ttu-id="8ddd8-181">Cada subnodo del árbol corresponde a un subelemento del `client` elemento <> del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-181">Every sub-node in the tree corresponds to a sub-element of the <`client`> element in the configuration file.</span></span>

<span data-ttu-id="8ddd8-182">Al hacer clic en el nodo **cliente** , puede ver o realizar tareas en la **Página de Resumen** del cliente en el **Panel de detalles**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-182">When you click the **Client** node, you can view or perform tasks on the client **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-client-endpoint-configuration"></a><span data-ttu-id="8ddd8-183">Crear una nueva configuración de punto de conexión de cliente</span><span class="sxs-lookup"><span data-stu-id="8ddd8-183">Creating a new Client Endpoint Configuration</span></span>

<span data-ttu-id="8ddd8-184">Puede crear una nueva configuración de extremo de cliente de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-184">You can create a new client endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="8ddd8-185">Crear por asistente: haga clic en el vínculo **crear un nuevo cliente...**</span><span class="sxs-lookup"><span data-stu-id="8ddd8-185">Create by Wizard: Click the link **Create a New Client…**</span></span> <span data-ttu-id="8ddd8-186">en el **Panel de tareas** de la parte inferior izquierda de la ventana o en la **Página de Resumen** para iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-186">on the **Task Pane** on the lower-left of the window, or **Summary Page** to launch the wizard.</span></span> <span data-ttu-id="8ddd8-187">También puede hacerlo en el menú **archivo** -> **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-187">You can also do so in the **File** menu -> **Add New Item**.</span></span> <span data-ttu-id="8ddd8-188">El asistente le pedirá que indique la ubicación de la configuración de servicio, a partir de la cual se genera la configuración del cliente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-188">The wizard prompts you to point to the location of the service configuration, from which the client configuration is generated.</span></span> <span data-ttu-id="8ddd8-189">A continuación podrá elegir el punto de conexión de servicio con el que conectarse.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-189">You can then choose the service endpoint to connect to.</span></span>

- <span data-ttu-id="8ddd8-190">Crear manualmente: haga clic con el botón secundario en el nodo **extremos** , en **cliente**, y elija **nuevo punto de conexión de cliente**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-190">Create manually: Right-click the **Endpoints** node under **Client**, and choose **New Client Endpoint**.</span></span>

#### <a name="editing-a-client-endpoint-configuration"></a><span data-ttu-id="8ddd8-191">Editar una configuración de punto de conexión de cliente</span><span class="sxs-lookup"><span data-stu-id="8ddd8-191">Editing a Client Endpoint Configuration</span></span>

1. <span data-ttu-id="8ddd8-192">Haga clic en un nodo de **punto de conexión de cliente** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-192">Click a **Client Endpoint** node.</span></span>

2. <span data-ttu-id="8ddd8-193">Edite la configuración en la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-193">Edit the settings in the property grids.</span></span>

### <a name="standard-endpoint"></a><span data-ttu-id="8ddd8-194">punto de conexión estándar</span><span class="sxs-lookup"><span data-stu-id="8ddd8-194">Standard Endpoint</span></span>

<span data-ttu-id="8ddd8-195">Los puntos de conexión estándar son puntos de conexión especializados que tienen uno o más aspectos de la dirección, contrato y enlace definidos en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-195">Standard endpoints are specialized endpoints that have one or more aspects of the address, contract and binding set to default values.</span></span>

<span data-ttu-id="8ddd8-196">Estos valores de configuración se almacenan en el nodo de **punto de conexión estándar** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-196">Such configuration settings are stored in the **Standard Endpoint** node.</span></span> <span data-ttu-id="8ddd8-197">El nodo **punto de conexión estándar** muestra todos los valores de punto de conexión estándar en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-197">The **Standard Endpoint** node displays all of the standard endpoint settings in the configuration file.</span></span> <span data-ttu-id="8ddd8-198">Cada subnodo del árbol corresponde a un subelemento del `<standardEndpoints>` elemento en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-198">Every sub-node in the tree corresponds to a sub-element in the `<standardEndpoints>` element in the configuration file.</span></span>

<span data-ttu-id="8ddd8-199">Al hacer clic en el nodo **extremo estándar** , puede ver o realizar tareas en la **página Resumen** de punto de conexión estándar en el **Panel de detalles**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-199">When you click the **Standard Endpoint** node, you can view or perform tasks on the standard endpoint **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-standard-endpoint-configuration"></a><span data-ttu-id="8ddd8-200">Crear una nueva configuración de punto de conexión estándar</span><span class="sxs-lookup"><span data-stu-id="8ddd8-200">Creating a New Standard Endpoint Configuration</span></span>

<span data-ttu-id="8ddd8-201">Puede crear una nueva configuración de punto de conexión estándar de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-201">You can create a new standard endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="8ddd8-202">Haga clic con el botón secundario en el nodo **punto de conexión estándar** y seleccione **nueva configuración de extremo estándar...**</span><span class="sxs-lookup"><span data-stu-id="8ddd8-202">Right-click the **Standard Endpoint** node and select **New Standard Endpoint Configuration…**</span></span> <span data-ttu-id="8ddd8-203">Seleccione el tipo de enlace en el cuadro de diálogo y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-203">Select the binding type in the dialog box and click **OK**.</span></span>

- <span data-ttu-id="8ddd8-204">Seleccione el nodo **punto de conexión estándar** y haga clic en **nueva configuración de extremo estándar...**</span><span class="sxs-lookup"><span data-stu-id="8ddd8-204">Select the **Standard Endpoint** node and click **New Standard Endpoint Configuration…**</span></span> <span data-ttu-id="8ddd8-205">en el **Panel de tareas** de la parte inferior izquierda de la ventana.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-205">in the **Task Pane** on the lower-left of the window.</span></span>

<span data-ttu-id="8ddd8-206">En el cuadro de diálogo **crear un nuevo extremo estándar** se muestra y se enumeran todos los tipos de punto de conexión estándar registrados.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-206">The **Creating a New Standard Endpoint** dialog box displays and lists all registered standard endpoint types.</span></span>

#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a><span data-ttu-id="8ddd8-207">Ver y editar una configuración de punto de conexión estándar</span><span class="sxs-lookup"><span data-stu-id="8ddd8-207">Viewing and Editing a Standard Endpoint Configuration</span></span>

<span data-ttu-id="8ddd8-208">Puede abrir una configuración de extremo estándar para verla y editarla de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-208">You can open a standard endpoint configuration for viewing and editing in the following ways:</span></span>

- <span data-ttu-id="8ddd8-209">Haga clic para expandir el nodo **punto de conexión estándar** y haga clic en el subnodo del extremo respectivo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-209">Click to expand the **Standard Endpoint** node and click the respective endpoint sub-node.</span></span>

- <span data-ttu-id="8ddd8-210">Haga clic en el nodo **extremo estándar** y haga clic en el punto de conexión respectivo en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-210">Click the **Standard Endpoint** node and click the respective endpoint on the Detail pane.</span></span>

<span data-ttu-id="8ddd8-211">Los atributos para el punto de conexión se muestran en el panel derecho para edición.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-211">Attributes for the endpoint are shown in the right pane for editing.</span></span>

#### <a name="deleting-a-standard-endpoint-configuration"></a><span data-ttu-id="8ddd8-212">Eliminar una configuración de punto de conexión estándar</span><span class="sxs-lookup"><span data-stu-id="8ddd8-212">Deleting a Standard Endpoint Configuration</span></span>

<span data-ttu-id="8ddd8-213">Puede eliminar una configuración de punto de conexión estándar de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-213">You can delete a standard endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="8ddd8-214">Haga clic para expandir el nodo **punto de conexión estándar** y haga clic con el botón secundario en el subnodo del extremo respectivo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-214">Click to expand the **Standard Endpoint** node and right-click the respective endpoint sub-node.</span></span> <span data-ttu-id="8ddd8-215">Use el comando de contexto **Eliminar configuración de extremo estándar** para eliminar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-215">Use the context command **Delete Standard Endpoint Configuration** to delete the endpoint.</span></span>

- <span data-ttu-id="8ddd8-216">Haga clic en el nodo **punto de conexión estándar** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-216">Click the **Standard Endpoint** node.</span></span> <span data-ttu-id="8ddd8-217">En el panel de **tareas** , haga clic en **Eliminar configuración de extremo estándar**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-217">In the **Task** pane, click **Delete Standard Endpoint Configuration**.</span></span>

<span data-ttu-id="8ddd8-218">Si el extremo estándar está en uso, se muestra un mensaje de advertencia al intentar eliminarlo: **el extremo estándar está en uso. Si lo elimina ahora, asegúrese de eliminar todas sus referencias en otras partes de la configuración (por ejemplo, en el punto de conexión de servicio o punto de conexión de cliente). De lo contrario, la configuración no será válida y no se podrá abrir la próxima vez. ¿Está seguro de que desea eliminar el extremo estándar? "**</span><span class="sxs-lookup"><span data-stu-id="8ddd8-218">If the standard endpoint is in used, a warning message is displayed when you attempt to delete it: **The standard endpoint is in use. If you delete it now, please be sure to delete all of its references in other parts of the configuration (for example, in the service endpoint or client endpoint). Otherwise, the configuration will be invalid and cannot be opened next time. Are you sure you want to delete the standard endpoint?"**</span></span>

### <a name="binding"></a><span data-ttu-id="8ddd8-219">Enlace</span><span class="sxs-lookup"><span data-stu-id="8ddd8-219">Binding</span></span>

<span data-ttu-id="8ddd8-220">Las configuraciones de enlace se usan para configurar enlaces en extremos.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-220">Binding configurations are used to configure bindings on endpoints.</span></span> <span data-ttu-id="8ddd8-221">Estos valores de configuración se almacenan en el nodo de **enlace** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-221">Such configuration settings are stored in the **Binding** node.</span></span> <span data-ttu-id="8ddd8-222">Los puntos de conexión hacen referencia a las configuraciones de enlace por nombre y varios puntos de conexión pueden hacer referencia a una configuración de enlace única.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-222">Endpoints reference binding configurations by name and multiple endpoints can reference a single binding configuration.</span></span>

<span data-ttu-id="8ddd8-223">El nodo **enlaces** muestra todos los valores de enlace en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-223">The **Bindings** node displays all of the binding settings in the configuration file.</span></span> <span data-ttu-id="8ddd8-224">Cada subnodo del árbol corresponde a un subelemento del `bindings` elemento <> del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-224">Every sub-node in the tree corresponds to a sub-element in the <`bindings`> element in the configuration file.</span></span>

<span data-ttu-id="8ddd8-225">Al hacer clic en el nodo **enlaces** , puede ver o realizar tareas en la **página Resumen** de enlace en el **Panel de detalles**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-225">When you click the **Bindings** node, you can view or perform tasks on the binding **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-binding-configuration"></a><span data-ttu-id="8ddd8-226">Crear una nueva configuración de enlace</span><span class="sxs-lookup"><span data-stu-id="8ddd8-226">Creating a New Binding Configuration</span></span>

<span data-ttu-id="8ddd8-227">Puede crear una nueva configuración de enlace de las maneras siguientes.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-227">You can create a new binding configuration in the following ways.</span></span>

- <span data-ttu-id="8ddd8-228">Haga clic con el botón secundario en el nodo **enlaces** y seleccione **nueva configuración de enlace**...</span><span class="sxs-lookup"><span data-stu-id="8ddd8-228">Right-click the **Bindings** node and select **New Binding Configuration**…</span></span> <span data-ttu-id="8ddd8-229">Seleccione el tipo de enlace en el cuadro de diálogo y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-229">Select the binding type in the dialog box and click **OK**.</span></span>

- <span data-ttu-id="8ddd8-230">Seleccione el nodo **enlaces** y haga clic en **nueva configuración de enlace**...</span><span class="sxs-lookup"><span data-stu-id="8ddd8-230">Select the **Bindings** node and click **New Binding Configuration**…</span></span> <span data-ttu-id="8ddd8-231">en el **Panel de tareas** de la parte inferior izquierda de la ventana.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-231">in the **Task Pane** on the lower-left of the window.</span></span>

- <span data-ttu-id="8ddd8-232">En la página Resumen de servicio o cliente, haga clic **en haga clic para crear** en el campo **configuración de enlace** para crear una configuración de enlace para el punto de conexión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-232">In the service or client summary page, click **Click to Create** in the **Binding Configuration** field to create a binding configuration for the corresponding endpoint.</span></span>

#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a><span data-ttu-id="8ddd8-233">Agregar extensiones de elemento de enlace a un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="8ddd8-233">Adding Binding Element Extensions to a Custom Binding</span></span>

1. <span data-ttu-id="8ddd8-234">Seleccione el enlace al que desea agregar un elemento de extensión.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-234">Select the binding you want to add an extension element to.</span></span>

2. <span data-ttu-id="8ddd8-235">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-235">Click **Add**.</span></span>

3. <span data-ttu-id="8ddd8-236">De la lista de extensiones disponibles, seleccione la extensión de elemento de enlace que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-236">From the list of available extensions, select the binding element extension you want to add.</span></span> <span data-ttu-id="8ddd8-237">Para seleccionar varios elementos, presione simultáneamente la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-237">To select multiple items, press the CTRL key simultaneously.</span></span>

4. <span data-ttu-id="8ddd8-238">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-238">Click **Add**.</span></span>

#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a><span data-ttu-id="8ddd8-239">Ajustar la posición de la extensión en un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="8ddd8-239">Adjusting the Extension Position in a Custom Binding</span></span>

<span data-ttu-id="8ddd8-240">Un enlace personalizado es una colección de elementos de enlace que forman una pila.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-240">A custom binding is a collection of binding elements that form a stack.</span></span> <span data-ttu-id="8ddd8-241">Cada elemento de enlace en la pila tiene su propia configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-241">Each binding element on the stack has its own configuration settings.</span></span> <span data-ttu-id="8ddd8-242">El orden de las extensiones de elemento de enlace en un enlace personalizado indica sus posiciones en la pila.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-242">The order of the binding element extensions in a custom binding indicates their positions in the stack.</span></span> <span data-ttu-id="8ddd8-243">Se aplican primero los elementos de la parte superior de la pila.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-243">Elements at the top of the stack are applied first.</span></span> <span data-ttu-id="8ddd8-244">Para cambiar el orden:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-244">To change the ordering:</span></span>

1. <span data-ttu-id="8ddd8-245">Seleccione el nodo de enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-245">Select the custom binding node.</span></span>

2. <span data-ttu-id="8ddd8-246">Seleccione un elemento de extensión de enlace en la sección **posición de extensión de elemento de enlace** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-246">Select one binding extension element in the **Binding Element Extension Position** section.</span></span>

3. <span data-ttu-id="8ddd8-247">Use el botón **arriba** o **abajo** situado en el lado izquierdo de la lista para cambiar la posición del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-247">Use the **Up** or **Down** button on the left side of the list to change the position of the selected element.</span></span>

#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a><span data-ttu-id="8ddd8-248">Editar la configuración de extensiones de elemento de enlace en un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="8ddd8-248">Editing the Configuration of Binding Element Extensions in a Custom Binding</span></span>

1. <span data-ttu-id="8ddd8-249">Seleccione el nodo de enlace en el árbol.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-249">Select the binding node in the tree.</span></span>

2. <span data-ttu-id="8ddd8-250">Seleccione el enlace personalizado que contiene el elemento que desea editar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-250">Select the custom binding that contains the element you want to edit.</span></span>

3. <span data-ttu-id="8ddd8-251">Seleccione la extensión de elemento de enlace que desea editar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-251">Select the binding element extension you want to edit.</span></span> <span data-ttu-id="8ddd8-252">La configuración del elemento aparece en el panel derecho, donde se puede editar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-252">The settings of the element appear in the right pane, where they can be edited.</span></span>

### <a name="diagnostics"></a><span data-ttu-id="8ddd8-253">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="8ddd8-253">Diagnostics</span></span>

<span data-ttu-id="8ddd8-254">El nodo **diagnósticos** muestra toda la configuración de diagnóstico en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-254">The **Diagnostics** node displays all of the diagnostic settings in the configuration file.</span></span> <span data-ttu-id="8ddd8-255">Permite activar o desactivar los contadores de rendimiento, habilitar o deshabilitar Instrumental de administración de Windows (WMI), configurar el seguimiento de WCF y configurar el registro de mensajes de WCF.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-255">It enables you to turn performance counters on or off, enable or disable Windows Management Instrumentation (WMI), configure WCF tracing, and configure WCF message logging.</span></span> <span data-ttu-id="8ddd8-256">La configuración del nodo **diagnósticos** corresponde a la `system.diagnostics` sección <> y `<diagnostics>` en `<system.serviceModel>` el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-256">The settings in the **Diagnostics** node correspond to the <`system.diagnostics`> section, and `<diagnostics>` section in `<system.serviceModel>` in the configuration file.</span></span>

<span data-ttu-id="8ddd8-257">Al hacer clic en el nodo **diagnósticos** , puede ver o realizar tareas en la **página Resumen** de diagnósticos en el **Panel de detalles**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-257">When you click the **Diagnostics** node, you can view or perform tasks on the diagnostics **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="configuring-performance-counters-and-wmi"></a><span data-ttu-id="8ddd8-258">Configurar contadores de rendimiento y WMI</span><span class="sxs-lookup"><span data-stu-id="8ddd8-258">Configuring performance counters and WMI</span></span>

1. <span data-ttu-id="8ddd8-259">Haga clic en el nodo **diagnósticos** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-259">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="8ddd8-260">Haga clic en **alternar contadores de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-260">Click **Toggle Performance Counters**.</span></span> <span data-ttu-id="8ddd8-261">El contador de rendimiento tiene tres estados: Apagado (valor predeterminado), ServiceOnly y todos.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-261">The performance counter has three states: Off (default), ServiceOnly, and All.</span></span> <span data-ttu-id="8ddd8-262">Al hacer clic en el vínculo, se alterna el valor entre estos tres estados.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-262">Clicking the link toggles the setting among these three states.</span></span>

#### <a name="configuring-wmi-provider"></a><span data-ttu-id="8ddd8-263">Configurar proveedor de WMI</span><span class="sxs-lookup"><span data-stu-id="8ddd8-263">Configuring WMI Provider</span></span>

1. <span data-ttu-id="8ddd8-264">Haga clic en el nodo **diagnósticos** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-264">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="8ddd8-265">Para habilitar el proveedor de WMI, haga clic en el vínculo **Habilitar proveedor WMI** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-265">To enable WMI provider, click the **Enable WMI Provider** link.</span></span>

#### <a name="enabling-wcf-tracing"></a><span data-ttu-id="8ddd8-266">Habilitar la traza WCF</span><span class="sxs-lookup"><span data-stu-id="8ddd8-266">Enabling WCF Tracing</span></span>

<span data-ttu-id="8ddd8-267">Puede crear un archivo de seguimiento de WCF con propiedades estándar o configurar un archivo de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-267">You can create a WCF trace file with standard properties or set up a custom trace file.</span></span>

1. <span data-ttu-id="8ddd8-268">Haga clic en el nodo **diagnósticos** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-268">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="8ddd8-269">Haga clic en **Habilitar seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-269">Click **Enable Tracing**.</span></span>

3. <span data-ttu-id="8ddd8-270">Haga clic en el vínculo **nivel de seguimiento** para ajustar el nivel de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-270">Click the **Trace Level** link to adjust the trace level.</span></span> <span data-ttu-id="8ddd8-271">Hay seis niveles de seguimiento: apagado, crítico, error, advertencia, información y detallado.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-271">There are six trace levels: Off, Critical, Error, Warning, Information, and Verbose.</span></span> <span data-ttu-id="8ddd8-272">La opción **seguimiento de actividad** y **propagar actividad** le permiten usar la característica de seguimiento de la actividad WCF.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-272">The **Activity Tracing** and **Propagate Activity** option enable you to use the WCF activity tracing feature.</span></span>

4. <span data-ttu-id="8ddd8-273">Haga clic en el nombre del agente de escucha de traza para especificar el archivo y las opciones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-273">Click the trace listener name to specify the trace file and options.</span></span>

#### <a name="enabling-wcf-logging"></a><span data-ttu-id="8ddd8-274">Habilitar el registro del WCF</span><span class="sxs-lookup"><span data-stu-id="8ddd8-274">Enabling WCF Logging</span></span>

<span data-ttu-id="8ddd8-275">Puede crear un archivo de seguimiento de WCF con propiedades estándar o configurar un archivo de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-275">You can create a WCF trace file with standard properties or set up a custom trace file.</span></span>

1. <span data-ttu-id="8ddd8-276">Haga clic en el nodo **diagnósticos** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-276">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="8ddd8-277">Haga clic en **Habilitar registro de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-277">Click **Enable Message Logging**.</span></span>

3. <span data-ttu-id="8ddd8-278">Haga clic en el vínculo **nivel de registro** para ajustar el nivel de registro.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-278">Click the **Log Level** link to adjust the log level.</span></span> <span data-ttu-id="8ddd8-279">Hay tres niveles de registro: incorrecto, servicio y transporte.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-279">There are three log levels: Malformed, Service, and Transport.</span></span>

4. <span data-ttu-id="8ddd8-280">Haga clic en el nombre de agente de escucha para especificar el archivo y las opciones de registro.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-280">Click the listener name to specify the log file and options.</span></span>

> [!NOTE]
> <span data-ttu-id="8ddd8-281">Si desea que los registros de seguimiento y de mensajes se vacíen automáticamente cuando se cierre la aplicación, habilite la opción **vaciado automático** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-281">If you want the trace and message logs to be flushed automatically when your application is closed, enable the **Auto Flush** option.</span></span>

<span data-ttu-id="8ddd8-282">La **Página de Resumen** de **diagnósticos** le permite realizar las tareas más comunes en la configuración de diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-282">The **Diagnostics** **Summary Page** enables you to accomplish the most common tasks in configuring diagnostics.</span></span> <span data-ttu-id="8ddd8-283">Sin embargo, si desea modificar manualmente la configuración de los agentes de escucha y los orígenes, debe expandir el nodo **diagnósticos** y editar la configuración en el nodo **registro de mensajes**, **agentes de escucha** y **orígenes** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-283">However, if you want to manually edit the Listeners and Sources settings, you must expand the **Diagnostics** node and edit settings in **Message Logging**, **Listeners** and **Sources** node.</span></span>

#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a><span data-ttu-id="8ddd8-284">Habilitar traza personalizada o registro de mensajes de WCF</span><span class="sxs-lookup"><span data-stu-id="8ddd8-284">Enabling WCF Custom Tracing or Message Logging</span></span>

1. <span data-ttu-id="8ddd8-285">Haga clic en el nodo **diagnósticos** y expándalo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-285">Click the **Diagnostics** node, and expand it.</span></span>

2. <span data-ttu-id="8ddd8-286">Haga clic con el botón secundario en el nodo **agentes de escucha** y seleccione **nuevo agente de escucha**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-286">Right-click the **Listeners** node and select **New Listener**.</span></span>

3. <span data-ttu-id="8ddd8-287">Escriba el nombre del archivo de seguimiento en el campo **InitData** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-287">Type in the trace file name in the **InitData** field.</span></span> <span data-ttu-id="8ddd8-288">Puede hacer clic en el para ir a una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-288">You can click the "…" button to browse to a path.</span></span>

4. <span data-ttu-id="8ddd8-289">Al hacer clic en la línea **TypeName** , se muestra una "..." botón.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-289">Clicking the **TypeName** line displays a "…" button.</span></span> <span data-ttu-id="8ddd8-290">Haga clic en este botón para abrir el **Explorador de tipos de agente de escucha de seguimiento**, que puede usar para buscar agentes de escucha de seguimiento preconfigurados que ya están instalados.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-290">Click this button to open the **Trace Listener Type Browser**, which you can use to find pre-configured trace listeners that are already installed.</span></span>

5. <span data-ttu-id="8ddd8-291">Observe la sección **origen** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-291">Note the **Source** section.</span></span> <span data-ttu-id="8ddd8-292">Haga clic en **Agregar** en esta sección para abrir un cuadro de diálogo con un menú desplegable que muestra los orígenes de seguimiento disponibles.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-292">Click **Add** in this section to open a dialog box with a drop-down menu, which lists available tracing sources.</span></span> <span data-ttu-id="8ddd8-293">Seleccione un origen de traza y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-293">Select a tracing source and click **OK**.</span></span>

6. <span data-ttu-id="8ddd8-294">Para editar la configuración del registro de mensajes, haga clic en el nodo **registro de mensajes** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-294">To edit Message Logging settings, click the **Message Logging** node.</span></span> <span data-ttu-id="8ddd8-295">Puede editar los valores en la cuadrícula de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-295">You can edit the settings in the property grid.</span></span>

### <a name="advanced"></a><span data-ttu-id="8ddd8-296">Avanzado</span><span class="sxs-lookup"><span data-stu-id="8ddd8-296">Advanced</span></span>

#### <a name="behaviors"></a><span data-ttu-id="8ddd8-297">comportamientos</span><span class="sxs-lookup"><span data-stu-id="8ddd8-297">Behaviors</span></span>

<span data-ttu-id="8ddd8-298">El nodo **comportamientos** muestra los comportamientos que se definen actualmente en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-298">The **Behaviors** node displays the behaviors that are currently defined in the configuration file.</span></span>

<span data-ttu-id="8ddd8-299">Las configuraciones de comportamiento se utilizan para configurar comportamientos de puntos de conexión y servicios.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-299">Behavior configurations are used to configure behaviors of endpoints and services.</span></span> <span data-ttu-id="8ddd8-300">Estos valores de configuración se almacenan en el nodo **avanzado** bajo **comportamientos de servicio** y **comportamientos de extremo**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-300">Such configuration settings are stored in the **Advanced** node under **Service Behaviors** and **Endpoint Behaviors**.</span></span> <span data-ttu-id="8ddd8-301">Los servicios utilizan comportamientos de servicios; pero los puntos de conexión utilizan comportamientos de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-301">Service behaviors are used by services; whereas endpoint behaviors by endpoints.</span></span>

<span data-ttu-id="8ddd8-302">Los comportamientos son una colección de elementos de extensión que forman una pila.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-302">Behaviors are a collection of extension elements that for a stack.</span></span> <span data-ttu-id="8ddd8-303">Se aplica primero el elemento en la parte superior de la pila.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-303">The element at the top of the stack is applied first.</span></span> <span data-ttu-id="8ddd8-304">Cada elemento de extensión puede tener su propia configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-304">Each extension element can have its own configuration.</span></span>

##### <a name="creating-a-new-behavior-configuration"></a><span data-ttu-id="8ddd8-305">Crear una nueva configuración de comportamiento</span><span class="sxs-lookup"><span data-stu-id="8ddd8-305">Creating a new Behavior Configuration</span></span>

<span data-ttu-id="8ddd8-306">Puede crear una nueva configuración de comportamiento de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-306">You can create a new behavior configuration in two ways.</span></span>

- <span data-ttu-id="8ddd8-307">Haga clic con el botón secundario en uno de los nodos de comportamiento y seleccione "**nueva configuración de comportamiento.** ..</span><span class="sxs-lookup"><span data-stu-id="8ddd8-307">Right-click one of the behavior nodes and select "**New Behavior Configuration…**</span></span>

- <span data-ttu-id="8ddd8-308">Seleccione uno de los nodos de comportamiento y haga clic en la **nueva configuración de comportamiento**...</span><span class="sxs-lookup"><span data-stu-id="8ddd8-308">Select one of the behavior nodes and click the **New Behavior Configuration**…</span></span> <span data-ttu-id="8ddd8-309">en el **Panel de tareas** de la parte inferior izquierda de la ventana.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-309">in the **Task Pane** on the lower-left of the window.</span></span>

##### <a name="adding-behavior-element-extensions-to-a-behavior"></a><span data-ttu-id="8ddd8-310">Agregar las extensiones de elemento de comportamiento a un comportamiento</span><span class="sxs-lookup"><span data-stu-id="8ddd8-310">Adding Behavior Element Extensions to a Behavior</span></span>

1. <span data-ttu-id="8ddd8-311">Seleccione uno de los nodos de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-311">Select one of the behavior nodes.</span></span>

2. <span data-ttu-id="8ddd8-312">Seleccione el comportamiento que desee editar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-312">Select the behavior you want edit.</span></span>

3. <span data-ttu-id="8ddd8-313">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-313">Click **Add**.</span></span>

4. <span data-ttu-id="8ddd8-314">De la lista de extensiones disponibles, seleccione la extensión de elemento de comportamiento que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-314">From the list of available extensions, select the behavior element extension you want to add.</span></span>

5. <span data-ttu-id="8ddd8-315">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-315">Click **Add**.</span></span>

##### <a name="adjusting-the-extension-position-in-a-behavior"></a><span data-ttu-id="8ddd8-316">Ajustar la posición de la extensión en un comportamiento</span><span class="sxs-lookup"><span data-stu-id="8ddd8-316">Adjusting the Extension Position in a Behavior</span></span>

<span data-ttu-id="8ddd8-317">Los comportamientos son colecciones de elementos que forman una pila.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-317">Behaviors are collections of elements that form a stack.</span></span> <span data-ttu-id="8ddd8-318">Cada elemento de la pila tiene su propia configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-318">Each element on the stack has its own configuration.</span></span> <span data-ttu-id="8ddd8-319">El orden de las extensiones de elemento de comportamiento en un comportamiento indica sus posiciones en la pila.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-319">The order of the behavior element extensions in a behavior indicates their positions in the stack.</span></span> <span data-ttu-id="8ddd8-320">Se aplican primero los elementos de la parte superior de la pila.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-320">Elements at the top of the stack are applied first.</span></span> <span data-ttu-id="8ddd8-321">Para cambiar el orden:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-321">To change the ordering:</span></span>

1. <span data-ttu-id="8ddd8-322">Seleccione uno de los nodos de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-322">Select one of the behavior nodes.</span></span>

2. <span data-ttu-id="8ddd8-323">Seleccione el comportamiento que desee editar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-323">Select the behavior you want edit.</span></span>

3. <span data-ttu-id="8ddd8-324">Seleccione un elemento de extensión de comportamiento en la sección **posición de extensión de elemento de comportamiento** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-324">Select a behavior extension element in the **Behavior Element Extension Position** section.</span></span>

4. <span data-ttu-id="8ddd8-325">Use el botón **arriba** o **abajo** situado en el lado izquierdo de la lista para cambiar la posición del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-325">Use the **Up** or **Down** button on the left side of the list to change the position of the selected element.</span></span>

##### <a name="editing-the-configuration-of-behavior-element-extensions"></a><span data-ttu-id="8ddd8-326">Editar la configuración de extensiones de elemento de comportamiento</span><span class="sxs-lookup"><span data-stu-id="8ddd8-326">Editing the Configuration of Behavior Element Extensions</span></span>

1. <span data-ttu-id="8ddd8-327">Seleccione uno de los nodos de comportamiento del árbol.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-327">Select one of the behavior nodes in the tree.</span></span>

2. <span data-ttu-id="8ddd8-328">Seleccione el comportamiento que contiene el elemento que desea editar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-328">Select the behavior that contains the element you want to edit.</span></span>

3. <span data-ttu-id="8ddd8-329">Seleccione la extensión de elemento de comportamiento que desea editar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-329">Select the behavior element extension you want to edit.</span></span> <span data-ttu-id="8ddd8-330">La configuración del elemento aparece en el panel derecho, donde se puede editar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-330">The settings of the element appear in the right pane where they can be edited.</span></span>

#### <a name="protocolmapping"></a><span data-ttu-id="8ddd8-331">ProtocolMapping</span><span class="sxs-lookup"><span data-stu-id="8ddd8-331">ProtocolMapping</span></span>

<span data-ttu-id="8ddd8-332">Esta sección permite establecer los tipos de enlaces predeterminados para los distintos protocolos como http, tcp, MSMQ o net.pipe mediante la asignación entre los esquemas de direcciones de protocolo y los posibles enlaces.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-332">This section allows you to set default binding types for different protocols such as http, tcp, MSMQ or net.pipe through defined mapping between protocol address schemes and the possible bindings.</span></span> <span data-ttu-id="8ddd8-333">También puede agregar nuevas asignaciones a otros protocolos.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-333">You can also add new mappings to other protocols.</span></span>

#### <a name="extensions"></a><span data-ttu-id="8ddd8-334">Extensiones</span><span class="sxs-lookup"><span data-stu-id="8ddd8-334">Extensions</span></span>

<span data-ttu-id="8ddd8-335">Las nuevas extensiones de enlace, extensiones de elemento de enlace, extensiones de punto de conexión estándar y extensiones de comportamiento se pueden registrar para su uso en la configuración de WCF.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-335">New binding extensions, binding element extensions, standard endpoint extensions and behavior extensions can be registered for use in WCF configuration.</span></span> <span data-ttu-id="8ddd8-336">Las extensiones son pares de nombre/tipo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-336">Extensions are name/type pairs.</span></span> <span data-ttu-id="8ddd8-337">El nombre define el nombre de la extensión en la configuración, mientras que el tipo implementa la extensión.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-337">The name defines the name of the extension in configuration, whereas the type implements the extension.</span></span> <span data-ttu-id="8ddd8-338">Hay cuatro tipos de extensiones:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-338">There are four types of extensions:</span></span>

- <span data-ttu-id="8ddd8-339">Las extensiones de enlace definen un tipo entero de enlace.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-339">Binding extensions define an entire binding type.</span></span> <span data-ttu-id="8ddd8-340">Ejemplo: `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-340">Example: `basicHttpBinding`.</span></span>

- <span data-ttu-id="8ddd8-341">Las extensiones de elemento de enlace definen un elemento de un enlace.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-341">Binding element extensions define an element of a binding.</span></span> <span data-ttu-id="8ddd8-342">Ejemplo: `textMessageEncoding`.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-342">Example: `textMessageEncoding`.</span></span>

- <span data-ttu-id="8ddd8-343">Las extensiones de extremo estándar definen un extremo estándar completo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-343">Standard endpoint extensions define an entire standard endpoint.</span></span> <span data-ttu-id="8ddd8-344">Ejemplo: `discoveryEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-344">Example: `discoveryEndpoint`.</span></span>

- <span data-ttu-id="8ddd8-345">Las extensiones de elemento de comportamiento definen un elemento de un comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-345">Behavior element extensions define an element of a behavior.</span></span> <span data-ttu-id="8ddd8-346">Ejemplo: `clientVia`.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-346">Example: `clientVia`.</span></span>

 <span data-ttu-id="8ddd8-347">Las extensiones registradas en configuración se pueden utilizar como cualquier otro componente WCF del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-347">Extensions that have been registered in configuration can be used like any other WCF component of the same type.</span></span>

##### <a name="adding-a-new-extension"></a><span data-ttu-id="8ddd8-348">Agregar una nueva extensión</span><span class="sxs-lookup"><span data-stu-id="8ddd8-348">Adding a new extension</span></span>

<span data-ttu-id="8ddd8-349">Seleccione uno de los nodos de extensión en los nodos avanzados:</span><span class="sxs-lookup"><span data-stu-id="8ddd8-349">Select one of the extension nodes in the advanced nodes:</span></span>

1. <span data-ttu-id="8ddd8-350">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-350">Click **New**.</span></span>

2. <span data-ttu-id="8ddd8-351">Escriba un nombre y tipo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-351">Enter a name and type.</span></span>

3. <span data-ttu-id="8ddd8-352">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-352">Click **OK**.</span></span>

4. <span data-ttu-id="8ddd8-353">La extensión aparece ahora en el lugar adecuado en el editor.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-353">The extension now appears in the appropriate place in the Editor.</span></span> <span data-ttu-id="8ddd8-354">Por ejemplo, si agrega una extensión de elemento de comportamiento, aparece en la lista de extensiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-354">For example, if you add a behavior element extension, it appears in the list of available extensions.</span></span>

#### <a name="hosting-environment"></a><span data-ttu-id="8ddd8-355">Entorno de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8ddd8-355">Hosting Environment</span></span>

<span data-ttu-id="8ddd8-356">Esta sección permite definir la configuración de creación de instancias para el entorno de hospedaje de servicio.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-356">This section allows you to define instantiation settings for the service hosting environment.</span></span>

### <a name="creating-a-configuration-file-using-the-wizard"></a><span data-ttu-id="8ddd8-357">Crear un archivo de configuración mediante el asistente</span><span class="sxs-lookup"><span data-stu-id="8ddd8-357">Creating a Configuration File Using the Wizard</span></span>

<span data-ttu-id="8ddd8-358">Una forma de crear un archivo de configuración nuevo es utilizar el Asistente para nuevo elemento de servicio.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-358">One way to create a new configuration file is to use the New Service Element Wizard.</span></span> <span data-ttu-id="8ddd8-359">El asistente busca los tipos de servicio instalados y otros elementos compatibles con WCF en el equipo, incluidos los directorios virtuales hospedados en Web y COM+, y los carga para que la creación de la configuración sea mucho más sencilla.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-359">The wizard finds the installed service types and other elements compatible with WCF on the computer, including COM+ and Web-hosted virtual directories, and loads them to make creating the configuration much more streamlined.</span></span>

#### <a name="creating-a-configuration-file"></a><span data-ttu-id="8ddd8-360">Crear un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8ddd8-360">Creating a Configuration File</span></span>

1. <span data-ttu-id="8ddd8-361">Inicie el editor de configuración de servicio mediante una ventana de comandos para navegar a la ubicación de instalación de WCF y, a continuación, escriba `SvcConfigEditor.exe` .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-361">Start Service Configuration Editor by using a command window to navigate to your WCF installation location, and then type `SvcConfigEditor.exe`.</span></span>

2. <span data-ttu-id="8ddd8-362">En el menú **archivo** , seleccione **abrir** y haga clic en **ejecutable**, **servicio com+** o **servicio hospedado en host**, dependiendo del tipo de archivo de configuración que desee crear.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-362">From the **File** menu, select **Open** and click **Executable**, **COM+ Service**, or **WebHosted Service**, depending on the type of configuration file you want to create.</span></span>

3. <span data-ttu-id="8ddd8-363">En el cuadro de diálogo **abrir** , navegue hasta el archivo específico para el que desea crear un archivo de configuración y haga doble clic en él.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-363">In the **Open** dialog box, navigate to the specific file you want to create a configuration file for and double-click it.</span></span>

4. <span data-ttu-id="8ddd8-364">En el menú **archivo** , seleccione **Agregar nuevo elemento** y haga clic en **servicio**.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-364">In the **File** menu, point to **Add New Item** and click **Service**.</span></span> <span data-ttu-id="8ddd8-365">Se abre el Asistente para nuevo elemento de servicio.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-365">The New Service Element Wizard opens.</span></span>

5. <span data-ttu-id="8ddd8-366">Siga los pasos en el asistente para crear el nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-366">Follow the steps in the wizard to create the new service.</span></span>

> [!NOTE]
> <span data-ttu-id="8ddd8-367">Si desea utilizar NetPeerTcpBinding del archivo de configuración generado por el asistente, tiene que agregar manualmente un elemento de configuración de enlace y modificar el atributo `mode` de su elemento `security` a "Ninguno".</span><span class="sxs-lookup"><span data-stu-id="8ddd8-367">If you want to use the NetPeerTcpBinding from the configuration file generated by the Wizard, you have to manually add a binding configuration element and modify the `mode` attribute of its `security` element to "None".</span></span>

## <a name="configuring-com"></a><span data-ttu-id="8ddd8-368">Configurar COM+</span><span class="sxs-lookup"><span data-stu-id="8ddd8-368">Configuring COM+</span></span>

<span data-ttu-id="8ddd8-369">El editor de configuración de servicio le permite crear un nuevo archivo de configuración para una aplicación COM+ existente o editar una configuración COM+ existente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-369">The Service Configuration Editor enables you to create a new configuration file for an existing COM+ application, or edit an existing COM+ configuration.</span></span> <span data-ttu-id="8ddd8-370">El nodo de **contrato com** solo está visible cuando la `comContract` sección <> existe en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-370">The **COM Contract** node is only visible when the <`comContract`> section exists in the configuration file.</span></span>

### <a name="creating-a-new-com-configuration"></a><span data-ttu-id="8ddd8-371">Crear una nueva configuración de COM+</span><span class="sxs-lookup"><span data-stu-id="8ddd8-371">Creating a New COM+ Configuration</span></span>

<span data-ttu-id="8ddd8-372">Antes de crear una nueva configuración de COM+, asegúrese de que su aplicación COM+ esté instalada en servicios de componente y registrada en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="8ddd8-372">Before creating a new COM+ configuration, make sure that your COM+ application is installed in Component Services, and registered in the Global Assembly Cache (GAC).</span></span>

1. <span data-ttu-id="8ddd8-373">Menú **archivo** : > **integrar**la  ->  **aplicación com+.**</span><span class="sxs-lookup"><span data-stu-id="8ddd8-373">Select **File** menu -> **Integrate** -> **COM+ Application.**</span></span> <span data-ttu-id="8ddd8-374">Esta operación cierra el archivo abierto actual.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-374">This operation closes the current opened file.</span></span> <span data-ttu-id="8ddd8-375">Si hay datos no guardados en el archivo actual, aparece el cuadro de diálogo Guardar.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-375">If there is unsaved data in the current file, a Save dialog appears.</span></span> <span data-ttu-id="8ddd8-376">A continuación, se inicia el **Asistente para la integración de com+** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-376">The **COM+ Integration Wizard** is then launched.</span></span>

2. <span data-ttu-id="8ddd8-377">En la primera página, seleccione la aplicación COM+ del árbol.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-377">In the first page, select the COM+ application from the tree.</span></span> <span data-ttu-id="8ddd8-378">Si no encuentra su aplicación COM+ en el árbol, compruebe que está instalada en los servicios de componente y registrada en la caché global de ensamblados (GAC).</span><span class="sxs-lookup"><span data-stu-id="8ddd8-378">If you cannot find your COM+ application in the tree, verify that it is installed in the Component Services and registered in the Global Assembly Cache (GAC).</span></span>

3. <span data-ttu-id="8ddd8-379">En la página siguiente, seleccione qué método(s) quiere exponer como servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-379">In the next page, select which method(s) you want to expose as WCF services.</span></span> <span data-ttu-id="8ddd8-380">Todos los métodos compatibles en la aplicación COM+ se muestran y se seleccionan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-380">All the supported methods in the COM+ application are displayed and selected by default.</span></span>

4. <span data-ttu-id="8ddd8-381">Elija un método de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-381">Choose a hosting method.</span></span>

5. <span data-ttu-id="8ddd8-382">Configure otros valores según las guías en el Asistente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-382">Configure other settings according to the guides in the wizard.</span></span>

6. <span data-ttu-id="8ddd8-383">El editor de configuración de servicio utiliza en segundo plano ComSvcConfig.exe para generar un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-383">Service Configuration Editor utilizes ComSvcConfig.exe in the background to generate configuration file.</span></span> <span data-ttu-id="8ddd8-384">Después de este paso, puede ver un resumen y salir del Asistente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-384">After this is completed, you can view a summary and exit the wizard.</span></span> <span data-ttu-id="8ddd8-385">Se abre el archivo de configuración generado para que pueda editarlo directamente.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-385">The generated configuration file is opened so that you can edit it directly.</span></span>

### <a name="editing-an-existing-com-configuration"></a><span data-ttu-id="8ddd8-386">Editar una configuración COM+ existente</span><span class="sxs-lookup"><span data-stu-id="8ddd8-386">Editing an Existing COM+ Configuration</span></span>

1. <span data-ttu-id="8ddd8-387">Seleccione el menú **archivo** -> **abrir**el  ->  **servicio com+**...</span><span class="sxs-lookup"><span data-stu-id="8ddd8-387">Select **File** menu -> **Open** -> **COM+ Service**…</span></span>

2. <span data-ttu-id="8ddd8-388">Seleccione el servicio COM+ que desee editar en la lista.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-388">Select the COM+ Service you want to edit from the list.</span></span>

3. <span data-ttu-id="8ddd8-389">Edite la configuración en el nodo **contratos com** .</span><span class="sxs-lookup"><span data-stu-id="8ddd8-389">Edit configuration settings in the **COM Contracts** node.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8ddd8-390">También puede abrir directamente un archivo de configuración que contenga contratos COM+ y modificarlo.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-390">You can also directly open and edit a configuration file that contains COM contracts.</span></span>

## <a name="security"></a><span data-ttu-id="8ddd8-391">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8ddd8-391">Security</span></span>

<span data-ttu-id="8ddd8-392">No se garantiza que un archivo de configuración de servicio generado por el editor de configuración sea seguro.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-392">A service configuration file generated by the Configuration Editor is not guaranteed to be secure.</span></span> <span data-ttu-id="8ddd8-393">Consulte la documentación de [seguridad](./feature-details/security.md) para averiguar cómo proteger los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-393">Please refer to the [Security](./feature-details/security.md) documentation to find out how to secure your WCF services.</span></span>

<span data-ttu-id="8ddd8-394">Además, el editor de configuración solo se puede utilizar para leer y escribir elementos de configuración de WCF válidos.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-394">In addition, the Configuration Editor can only be used to read and write valid WCF configuration elements.</span></span> <span data-ttu-id="8ddd8-395">La herramienta omite los elementos conformes a esquema definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-395">The tool ignores schema-compliant, user-defined elements.</span></span> <span data-ttu-id="8ddd8-396">Tampoco intenta quitar estos elementos del archivo de configuración o determinar sus efectos sobre los elementos de WCF conocidos.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-396">It also does not attempt remove these elements from the configuration file or determine their effects on the known WCF elements.</span></span> <span data-ttu-id="8ddd8-397">Es la responsabilidad del usuario determinar si estos elementos suponen una amenaza para la aplicación o el sistema.</span><span class="sxs-lookup"><span data-stu-id="8ddd8-397">It is the user’s responsibility to determine whether these elements pose a threat to the application or the system.</span></span>
