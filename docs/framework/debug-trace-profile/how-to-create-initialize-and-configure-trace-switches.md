---
title: Procedimiento para crear, inicializar y configurar modificadores de seguimiento
description: Crear, inicializar y configurar modificadores de seguimiento mediante las clases System. Diagnostics. BooleanSwitch y System. Diagnostics. TraceSwitch en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- trace switches, configuring
- tracing [.NET Framework], trace switches
- switches, trace
- tracing [.NET Framework], enabling or disabling
- Web.config configuration file, trace switches
ms.assetid: 5a0e41bf-f99c-4692-8799-f89617f5bcf9
ms.openlocfilehash: 4e8c076645f19e197ea820c052b20d5dde5e7565
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272259"
---
# <a name="how-to-create-initialize-and-configure-trace-switches"></a><span data-ttu-id="c975d-103">Procedimiento para crear, inicializar y configurar modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c975d-103">How to: Create, Initialize and Configure Trace Switches</span></span>

<span data-ttu-id="c975d-104">Los modificadores de seguimiento permiten habilitar, deshabilitar y filtrar la salida del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c975d-104">Trace switches enable you to enable, disable, and filter tracing output.</span></span>  
  
<a name="create"></a>

## <a name="creating-and-initializing-a-trace-switch"></a><span data-ttu-id="c975d-105">Crear e inicializar modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c975d-105">Creating and initializing a trace switch</span></span>  

 <span data-ttu-id="c975d-106">Para poder usar los modificadores de seguimiento, primero debe crearlos y colocarlos en el código.</span><span class="sxs-lookup"><span data-stu-id="c975d-106">In order to use trace switches, you must first create them and place them in your code.</span></span> <span data-ttu-id="c975d-107">Existen dos clases predefinidas desde las que puede crear objetos modificadores: la clase <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> y la clase <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c975d-107">There are two predefined classes from which you can create switch objects: the <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> class and the <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="c975d-108">Debe usar <xref:System.Diagnostics.BooleanSwitch> si solo le preocupa si aparece o no un mensaje de seguimiento, y <xref:System.Diagnostics.TraceSwitch> para distinguir entre los niveles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c975d-108">You would use <xref:System.Diagnostics.BooleanSwitch> if you care only about whether or not a tracing message appears; you would use <xref:System.Diagnostics.TraceSwitch> if you want to discriminate between levels of tracing.</span></span> <span data-ttu-id="c975d-109">Si utiliza <xref:System.Diagnostics.TraceSwitch>, puede definir sus propios mensajes de depuración y asociarlos a diferentes niveles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c975d-109">If you use a <xref:System.Diagnostics.TraceSwitch>, you can define your own debugging messages and associate them with different trace levels.</span></span> <span data-ttu-id="c975d-110">Puede utilizar ambos tipos de modificadores con el seguimiento o la depuración.</span><span class="sxs-lookup"><span data-stu-id="c975d-110">You can use both types of switches with either tracing or debugging.</span></span> <span data-ttu-id="c975d-111">De forma predeterminada, <xref:System.Diagnostics.BooleanSwitch> está deshabilitado y <xref:System.Diagnostics.TraceSwitch> está establecido en el nivel <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c975d-111">By default, a <xref:System.Diagnostics.BooleanSwitch> is disabled and a <xref:System.Diagnostics.TraceSwitch> is set to level <xref:System.Diagnostics.TraceLevel.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c975d-112">Los modificadores de seguimiento pueden crearse y colocarse en cualquier parte del código que pueda utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="c975d-112">Trace switches can be created and placed in any part of your code that might use them.</span></span>  
  
 <span data-ttu-id="c975d-113">Aunque puede establecer niveles de seguimiento y otras opciones de configuración en el código, le recomendamos que utilice el archivo de configuración para administrar el estado de los modificadores.</span><span class="sxs-lookup"><span data-stu-id="c975d-113">Although you can set trace levels and other configuration options in code, we recommend that you use the configuration file to manage the state of your switches.</span></span> <span data-ttu-id="c975d-114">El motivo es que administrar la configuración de los modificadores en el sistema de configuración le proporciona mayor flexibilidad: puede activar y desactivar los diversos modificadores y cambiar los niveles sin volver a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c975d-114">This is because managing the configuration of your switches in the configuration system gives you greater flexibility — you can turn on and off various switches and change levels without recompiling your application.</span></span>  
  
#### <a name="to-create-and-initialize-a-trace-switch"></a><span data-ttu-id="c975d-115">Para crear e inicializar modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c975d-115">To create and initialize a trace switch</span></span>  
  
1. <span data-ttu-id="c975d-116">Defina un modificador de tipo <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> o tipo <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> y establezca el nombre y la descripción del modificador.</span><span class="sxs-lookup"><span data-stu-id="c975d-116">Define a switch as either type <xref:System.Diagnostics.BooleanSwitch?displayProperty=nameWithType> or type <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> and set the name and description of the switch.</span></span>  
  
2. <span data-ttu-id="c975d-117">Configure el modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c975d-117">Configure your trace switch.</span></span> <span data-ttu-id="c975d-118">Para obtener más información, vea [configurar modificadores de seguimiento](#configure).</span><span class="sxs-lookup"><span data-stu-id="c975d-118">For more information, see [Configuring trace switches](#configure).</span></span>  
  
     <span data-ttu-id="c975d-119">El siguiente código crea dos modificadores, uno de cada tipo:</span><span class="sxs-lookup"><span data-stu-id="c975d-119">The following code creates two switches, one of each type:</span></span>  
  
    ```vb  
    Dim dataSwitch As New BooleanSwitch("Data", "DataAccess module")  
    Dim generalSwitch As New TraceSwitch("General", "Entire application")  
    ```  
  
    ```csharp  
    System.Diagnostics.BooleanSwitch dataSwitch =
       new System.Diagnostics.BooleanSwitch("Data", "DataAccess module");  
    System.Diagnostics.TraceSwitch generalSwitch =
       new System.Diagnostics.TraceSwitch("General",
       "Entire application");  
    ```  
  
<a name="configure"></a>

## <a name="configuring-trace-switches"></a><span data-ttu-id="c975d-120">Configuración de modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c975d-120">Configuring trace switches</span></span>  

 <span data-ttu-id="c975d-121">Después de que se distribuya la aplicación, puede habilitar o deshabilitar el resultado del seguimiento configurando los modificadores de seguimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c975d-121">After your application has been distributed, you can still enable or disable trace output by configuring the trace switches in your application.</span></span> <span data-ttu-id="c975d-122">Configurar un modificador consiste en cambiar su valor desde un origen externo después de que se inicialice.</span><span class="sxs-lookup"><span data-stu-id="c975d-122">Configuring a switch means changing its value from an external source after it has been initialized.</span></span> <span data-ttu-id="c975d-123">Puede cambiar los valores de los objetos modificadores con el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c975d-123">You can change the values of the switch objects using the configuration file.</span></span> <span data-ttu-id="c975d-124">Puede configurar un modificador de seguimiento para activarlo y desactivarlo, o para establecer su nivel y determinar la cantidad y el tipo de mensajes que pasa a los agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="c975d-124">You configure a trace switch to turn it on and off, or to set its level, determining the amount and type of messages it passes along to listeners.</span></span>  
  
 <span data-ttu-id="c975d-125">Los modificadores se configuran con el archivo .config.</span><span class="sxs-lookup"><span data-stu-id="c975d-125">Your switches are configured using the .config file.</span></span> <span data-ttu-id="c975d-126">En una aplicación web, es el archivo Web.config asociado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c975d-126">For a Web application, this is the Web.config file associated with the project.</span></span> <span data-ttu-id="c975d-127">En una aplicación de Windows, este archivo se denomina (nombre de la aplicación) .exe.config. En una aplicación implementada, este archivo debe residir en la misma carpeta que el ejecutable.</span><span class="sxs-lookup"><span data-stu-id="c975d-127">In a Windows application, this file is named (application name).exe.config. In a deployed application, this file must reside in the same folder as the executable.</span></span>  
  
 <span data-ttu-id="c975d-128">Cuando la aplicación ejecuta el código que crea una instancia de un modificador por primera vez, la aplicación comprueba el archivo de configuración para obtener información de nivel de seguimiento sobre el modificador con nombre.</span><span class="sxs-lookup"><span data-stu-id="c975d-128">When your application executes the code that creates an instance of a switch for the first time, it checks the configuration file for trace-level information about the named switch.</span></span> <span data-ttu-id="c975d-129">El sistema de seguimiento examina el archivo de configuración una sola vez con cada modificador, la primera vez que la aplicación crea el modificador.</span><span class="sxs-lookup"><span data-stu-id="c975d-129">The tracing system examines the configuration file only once for any particular switch — the first time your application creates the switch.</span></span>  
  
 <span data-ttu-id="c975d-130">En una aplicación implementada, el código de seguimiento se habilita volviendo a configurar los modificadores cuando la aplicación no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c975d-130">In a deployed application, you enable trace code by reconfiguring switch objects when your application is not running.</span></span> <span data-ttu-id="c975d-131">Normalmente, esto implica activar y desactivar los modificadores cambiando los niveles de seguimiento y, luego, reiniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c975d-131">Typically this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>  
  
 <span data-ttu-id="c975d-132">Cuando crea una instancia de un modificador, también la inicializa especificando dos argumentos: un argumento *displayName* y un argumento *description*.</span><span class="sxs-lookup"><span data-stu-id="c975d-132">When you create an instance of a switch, you also initialize it by specifying two arguments: a *displayName* argument and a *description* argument.</span></span> <span data-ttu-id="c975d-133">El argumento *displayName* del constructor establece la propiedad <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> de la instancia de clase <xref:System.Diagnostics.Switch>.</span><span class="sxs-lookup"><span data-stu-id="c975d-133">The *displayName* argument of the constructor sets the <xref:System.Diagnostics.Switch.DisplayName%2A?displayProperty=nameWithType> property of the <xref:System.Diagnostics.Switch> class instance.</span></span> <span data-ttu-id="c975d-134">*displayName* es el nombre que se usa para configurar el modificador en el archivo .config, y el argumento *description* debería devolver una breve descripción del modificador e indicar qué mensajes controla.</span><span class="sxs-lookup"><span data-stu-id="c975d-134">The *displayName* is the name that is used to configure the switch in the .config file, and the *description* argument should return a brief description of the switch and what messages it controls.</span></span>  
  
 <span data-ttu-id="c975d-135">Además de especificar el nombre de un modificador para configurarlo, también debe especificar un valor para el modificador.</span><span class="sxs-lookup"><span data-stu-id="c975d-135">In addition to specifying the name of a switch to configure, you must also specify a value for the switch.</span></span> <span data-ttu-id="c975d-136">El valor es un entero.</span><span class="sxs-lookup"><span data-stu-id="c975d-136">This value is an Integer.</span></span> <span data-ttu-id="c975d-137">Para <xref:System.Diagnostics.BooleanSwitch>, un valor de 0 corresponde a **Desactivado**, y cualquier valor distinto de cero corresponde a **Activado**.</span><span class="sxs-lookup"><span data-stu-id="c975d-137">For <xref:System.Diagnostics.BooleanSwitch>, a value of 0 corresponds to **Off**, and any nonzero value corresponds to **On**.</span></span> <span data-ttu-id="c975d-138">Para <xref:System.Diagnostics.TraceSwitch>, 0, 1, 2, 3 y 4 corresponden a **Desactivado**, **Error**, **Advertencia**, **Información** y **Detallado**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c975d-138">For <xref:System.Diagnostics.TraceSwitch>, 0,1,2,3, and 4 correspond **Off**, **Error**, **Warning**, **Info**, and **Verbose**, respectively.</span></span> <span data-ttu-id="c975d-139">Todos los números mayores de 4 se tratan como **Detallado**, y todos los números menores de cero se tratan como **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="c975d-139">Any number greater than 4 is treated as **Verbose**, and any number less than zero is treated as **Off**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c975d-140">En la versión 2.0 de .NET Framework, puede utilizar texto para especificar el valor de un modificador.</span><span class="sxs-lookup"><span data-stu-id="c975d-140">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="c975d-141">Por ejemplo, `true` para un <xref:System.Diagnostics.BooleanSwitch> o el texto que representa un valor de enumeración como `Error` para un <xref:System.Diagnostics.TraceSwitch>.</span><span class="sxs-lookup"><span data-stu-id="c975d-141">For example, `true` for a <xref:System.Diagnostics.BooleanSwitch> or the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="c975d-142">La línea `<add name="myTraceSwitch" value="Error" />` es equivalente a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="c975d-142">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
 <span data-ttu-id="c975d-143">Para que los usuarios finales puedan configurar los modificadores de seguimiento de una aplicación, debe proporcionar documentación detallada sobre los modificadores de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c975d-143">In order for end users to be able to configure an application's trace switches, you must provide detailed documentation on the switches in your application.</span></span> <span data-ttu-id="c975d-144">Debe detallar qué modificadores controlan qué y cómo activarlos y desactivarlos.</span><span class="sxs-lookup"><span data-stu-id="c975d-144">You should detail which switches control what and how to turn them on and off.</span></span> <span data-ttu-id="c975d-145">También debe proporcionar al usuario final un archivo .config con una ayuda apropiada en los comentarios.</span><span class="sxs-lookup"><span data-stu-id="c975d-145">You should also provide your end user with a .config file that has appropriate Help in the comments.</span></span>  
  
#### <a name="to-configure-trace-switches"></a><span data-ttu-id="c975d-146">Para configurar modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c975d-146">To configure trace switches</span></span>  
  
1. <span data-ttu-id="c975d-147">Para usar modificadores de seguimiento, primero debe crearlos y colocarlos en el código como se describe en la sección [Crear e inicializar modificadores de seguimiento](#create).</span><span class="sxs-lookup"><span data-stu-id="c975d-147">In order to use trace switches, you must first create them and place them in your code as described in the section [Creating and initializing a trace switch](#create).</span></span>  
  
2. <span data-ttu-id="c975d-148">Si el proyecto no contiene un archivo de configuración (app.config o Web.config), en el menú **Proyecto** seleccione **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="c975d-148">If your project does not contain a configuration file (app.config or Web.config), then from the **Project** menu, select **Add New Item**.</span></span>  
  
    - <span data-ttu-id="c975d-149">**Visual Basic:** en el cuadro de diálogo **Agregar nuevo elemento**, elija **Archivo de configuración de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c975d-149">**Visual Basic:** In the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
         <span data-ttu-id="c975d-150">El archivo de configuración de la aplicación se creará y se abrirá.</span><span class="sxs-lookup"><span data-stu-id="c975d-150">The application configuration file is created and opened.</span></span> <span data-ttu-id="c975d-151">Se trata de un documento XML cuyo elemento raíz es `<configuration>.`</span><span class="sxs-lookup"><span data-stu-id="c975d-151">This is an XML document whose root element is `<configuration>.`</span></span>  
  
    - <span data-ttu-id="c975d-152">**Visual C#:** en el cuadro de diálogo **Agregar nuevo elemento** elija **Archivo XML**.</span><span class="sxs-lookup"><span data-stu-id="c975d-152">**Visual C#:** In the **Add New Item** dialog box, choose **XML File**.</span></span> <span data-ttu-id="c975d-153">Asigne a este archivo el nombre **app.config**. En el editor XML, después de la declaración XML, agregue el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="c975d-153">Name this file **app.config**. In the XML editor, after the XML declaration, add the following XML:</span></span>  
  
        ```xml  
        <configuration>  
        </configuration>  
        ```  
  
         <span data-ttu-id="c975d-154">Cuando se compila el proyecto, el archivo app.config se copia en la carpeta de salida del proyecto y se cambia su nombre a *nombreDeLaAplicación*.exe.config.</span><span class="sxs-lookup"><span data-stu-id="c975d-154">When your project is compiled, the app.config file is copied to the project output folder and is renamed *applicationname*.exe.config.</span></span>  
  
3. <span data-ttu-id="c975d-155">Después de la etiqueta `<configuration>`, pero antes de la etiqueta `</configuration>`, agregue el código XML adecuado para configurar los modificadores.</span><span class="sxs-lookup"><span data-stu-id="c975d-155">After the `<configuration>` tag but before the `</configuration>` tag, add the appropriate XML to configure your switches.</span></span> <span data-ttu-id="c975d-156">En los ejemplos siguientes se muestra un **BooleanSwitch** con una propiedad **DisplayName** de `DataMessageSwitch` y un **TraceSwitch** con una propiedad **DisplayName** de `TraceLevelSwitch`.</span><span class="sxs-lookup"><span data-stu-id="c975d-156">The following examples demonstrate a **BooleanSwitch** with a **DisplayName** property of `DataMessageSwitch` and a **TraceSwitch** with a **DisplayName** property of `TraceLevelSwitch`.</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <add name="DataMessagesSwitch" value="0" />  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
     <span data-ttu-id="c975d-157">En esta configuración, ambos modificadores están desactivados.</span><span class="sxs-lookup"><span data-stu-id="c975d-157">In this configuration, both switches are off.</span></span>  
  
4. <span data-ttu-id="c975d-158">Si necesita activar **BooleanSwitch**, como `DataMessagesSwitch` mostrado en el ejemplo anterior, cambie **Value** por cualquier entero distinto de 0.</span><span class="sxs-lookup"><span data-stu-id="c975d-158">If you need to turn on a **BooleanSwitch**, such as `DataMessagesSwitch` shown in the previous example, change the **Value** to any integer other than 0.</span></span>  
  
5. <span data-ttu-id="c975d-159">Si necesita activar **TraceSwitch**, como `TraceLevelSwitch` mostrado en el ejemplo anterior, cambie **Value** por el ajuste del nivel adecuado (del 1 al 4).</span><span class="sxs-lookup"><span data-stu-id="c975d-159">If you need to turn on a **TraceSwitch**, such as `TraceLevelSwitch` shown in the previous example, change the **Value** to the appropriate level setting (1 to 4).</span></span>  
  
6. <span data-ttu-id="c975d-160">Agregue comentarios al archivo .config para que el usuario final entienda claramente qué valores debe cambiar para configurar los modificadores de la manera correcta.</span><span class="sxs-lookup"><span data-stu-id="c975d-160">Add comments to the .config file so the end user has a clear understanding of what values to change to configure the switches appropriately.</span></span>  
  
     <span data-ttu-id="c975d-161">En el ejemplo siguiente se muestra cómo podría quedar el código final, incluidos los comentarios:</span><span class="sxs-lookup"><span data-stu-id="c975d-161">The following example shows how the final code, including comments, might look:</span></span>  
  
    ```xml  
    <system.diagnostics>  
       <switches>  
          <!-- This switch controls data messages. In order to receive data   
             trace messages, change value="0" to value="1" -->  
          <add name="DataMessagesSwitch" value="0" />  
          <!-- This switch controls general messages. In order to   
             receive general trace messages change the value to the   
             appropriate level. "1" gives error messages, "2" gives errors   
             and warnings, "3" gives more detailed error information, and   
             "4" gives verbose trace information -->  
          <add name="TraceLevelSwitch" value="0" />  
       </switches>  
    </system.diagnostics>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c975d-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="c975d-162">See also</span></span>

- [<span data-ttu-id="c975d-163">Seguimiento e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c975d-163">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="c975d-164">Adición de instrucciones de seguimiento al código de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c975d-164">How to: Add Trace Statements to Application Code</span></span>](how-to-add-trace-statements-to-application-code.md)
- [<span data-ttu-id="c975d-165">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c975d-165">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="c975d-166">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="c975d-166">Trace and Debug Settings Schema</span></span>](../configure-apps/file-schema/trace-debug/index.md)
