---
description: 'Más información acerca de: Procedimiento: para escribir en el registro de eventos de una aplicación (Visual Basic)'
title: Procedimiento para escribir en el registro de eventos de una aplicación
ms.date: 07/20/2015
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
ms.openlocfilehash: ea53ff84f1fcf175912e35eb7433ece26886cf44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797294"
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a><span data-ttu-id="eff68-103">Cómo: Escribir en el registro de eventos de una aplicación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eff68-103">How to: Write to an Application Event Log (Visual Basic)</span></span>

<span data-ttu-id="eff68-104">Puede usar los objetos `My.Application.Log` y `My.Log` para escribir información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="eff68-104">You can use the `My.Application.Log` and `My.Log` objects to write information about events that occur in your application.</span></span> <span data-ttu-id="eff68-105">En este ejemplo se muestra cómo configurar un agente de escucha de registro de eventos para que `My.Application.Log` escriba información de seguimiento en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eff68-105">This example shows how to configure an event log listener so `My.Application.Log` writes tracing information to the Application event log.</span></span>

<span data-ttu-id="eff68-106">No se puede escribir en el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="eff68-106">You cannot write to the Security log.</span></span> <span data-ttu-id="eff68-107">Para poder escribir en el registro del sistema, debe ser miembro de la cuenta LocalSystem o Administrador.</span><span class="sxs-lookup"><span data-stu-id="eff68-107">In order to write to the System log, you must be a member of the LocalSystem or Administrator account.</span></span>

<span data-ttu-id="eff68-108">Para ver un registro de eventos, puede usar el **Explorador de servidores** o el **Visor de eventos de Windows**.</span><span class="sxs-lookup"><span data-stu-id="eff68-108">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="eff68-109">Para obtener más información, consulta [Eventos de ETW en .NET Framework](../../../../framework/performance/etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="eff68-109">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>

## <a name="to-add-and-configure-the-event-log-listener"></a><span data-ttu-id="eff68-110">Para agregar y configurar el agente de escucha de registro de eventos</span><span class="sxs-lookup"><span data-stu-id="eff68-110">To add and configure the event log listener</span></span>

1. <span data-ttu-id="eff68-111">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="eff68-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

    <span data-ttu-id="eff68-112">\- o -</span><span class="sxs-lookup"><span data-stu-id="eff68-112">\- or -</span></span>

    <span data-ttu-id="eff68-113">Si no hay ningún archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="eff68-113">If there is no app.config file,</span></span>

    1. <span data-ttu-id="eff68-114">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="eff68-114">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="eff68-115">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="eff68-115">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="eff68-116">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="eff68-116">Click **Add**.</span></span>

2. <span data-ttu-id="eff68-117">Ubique la sección `<listeners>` en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eff68-117">Locate the `<listeners>` section in the application configuration file.</span></span>

    <span data-ttu-id="eff68-118">Encontrará la sección `<listeners>` en la sección `<source>` con el atributo de nombre "DefaultSource", que está anidada bajo la sección `<system.diagnostics>` , anidada bajo la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="eff68-118">You will find the `<listeners>` section in the `<source>` section with the name attribute "DefaultSource", which is nested under the `<system.diagnostics>` section, which is nested under the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="eff68-119">Agregue este elemento a dicha sección `<listeners>` :</span><span class="sxs-lookup"><span data-stu-id="eff68-119">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="EventLog"/>
    ```

4. <span data-ttu-id="eff68-120">Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="eff68-120">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="eff68-121">Agregue este elemento a dicha sección `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="eff68-121">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="EventLog"
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="APPLICATION_NAME"/>
    ```

    <span data-ttu-id="eff68-122">Reemplace `APPLICATION_NAME` por el nombre de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="eff68-122">Replace `APPLICATION_NAME` with the name of your application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eff68-123">Normalmente, una aplicación escribe solo errores en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="eff68-123">Typically, an application writes only errors to the event log.</span></span> <span data-ttu-id="eff68-124">Para obtener información sobre el filtrado de la salida del registro, consulte [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="eff68-124">For information on filtering log output, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>

## <a name="to-write-event-information-to-the-event-log"></a><span data-ttu-id="eff68-125">Para escribir información de eventos en el registro de eventos</span><span class="sxs-lookup"><span data-stu-id="eff68-125">To write event information to the event log</span></span>

<span data-ttu-id="eff68-126">Use el método `My.Application.Log.WriteEntry` o `My.Application.Log.WriteException` para escribir información en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="eff68-126">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the event log.</span></span> <span data-ttu-id="eff68-127">Para obtener más información, vea [Cómo: Escribir mensajes de registro](how-to-write-log-messages.md) y [Cómo: Registrar excepciones](how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="eff68-127">For more information, see [How to: Write Log Messages](how-to-write-log-messages.md) and [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

<span data-ttu-id="eff68-128">Después de configurar el agente de escucha de registro de eventos para un ensamblado, este recibe todos los mensajes que `My.Application.Log` escribe desde ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="eff68-128">After you configure the event log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="eff68-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="eff68-129">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="eff68-130">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="eff68-130">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="eff68-131">Cómo: Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="eff68-131">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="eff68-132">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="eff68-132">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
