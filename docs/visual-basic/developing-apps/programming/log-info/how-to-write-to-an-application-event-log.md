---
title: 'Cómo: Escribir el registro de eventos de una aplicación'
ms.date: 07/20/2015
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
ms.openlocfilehash: 298d6d85f8b21176b72db8e676617577eb03fada
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410041"
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a><span data-ttu-id="4d819-102">Cómo: Escribir en el registro de eventos de una aplicación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d819-102">How to: Write to an Application Event Log (Visual Basic)</span></span>

<span data-ttu-id="4d819-103">Puede usar los objetos `My.Application.Log` y `My.Log` para escribir información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d819-103">You can use the `My.Application.Log` and `My.Log` objects to write information about events that occur in your application.</span></span> <span data-ttu-id="4d819-104">En este ejemplo se muestra cómo configurar un agente de escucha de registro de eventos para que `My.Application.Log` escriba información de seguimiento en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d819-104">This example shows how to configure an event log listener so `My.Application.Log` writes tracing information to the Application event log.</span></span>

<span data-ttu-id="4d819-105">No se puede escribir en el registro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d819-105">You cannot write to the Security log.</span></span> <span data-ttu-id="4d819-106">Para poder escribir en el registro del sistema, debe ser miembro de la cuenta LocalSystem o Administrador.</span><span class="sxs-lookup"><span data-stu-id="4d819-106">In order to write to the System log, you must be a member of the LocalSystem or Administrator account.</span></span>

<span data-ttu-id="4d819-107">Para ver un registro de eventos, puede usar el **Explorador de servidores** o el **Visor de eventos de Windows**.</span><span class="sxs-lookup"><span data-stu-id="4d819-107">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="4d819-108">Para obtener más información, consulta [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="4d819-108">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>

## <a name="to-add-and-configure-the-event-log-listener"></a><span data-ttu-id="4d819-109">Para agregar y configurar el agente de escucha de registro de eventos</span><span class="sxs-lookup"><span data-stu-id="4d819-109">To add and configure the event log listener</span></span>

1. <span data-ttu-id="4d819-110">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4d819-110">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

    <span data-ttu-id="4d819-111">\- o -</span><span class="sxs-lookup"><span data-stu-id="4d819-111">\- or -</span></span>

    <span data-ttu-id="4d819-112">Si no hay ningún archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="4d819-112">If there is no app.config file,</span></span>

    1. <span data-ttu-id="4d819-113">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="4d819-113">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="4d819-114">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="4d819-114">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="4d819-115">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4d819-115">Click **Add**.</span></span>

2. <span data-ttu-id="4d819-116">Ubique la sección `<listeners>` en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d819-116">Locate the `<listeners>` section in the application configuration file.</span></span>

    <span data-ttu-id="4d819-117">Encontrará la sección `<listeners>` en la sección `<source>` con el atributo de nombre "DefaultSource", que está anidada bajo la sección `<system.diagnostics>` , anidada bajo la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="4d819-117">You will find the `<listeners>` section in the `<source>` section with the name attribute "DefaultSource", which is nested under the `<system.diagnostics>` section, which is nested under the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="4d819-118">Agregue este elemento a dicha sección `<listeners>` :</span><span class="sxs-lookup"><span data-stu-id="4d819-118">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="EventLog"/>
    ```

4. <span data-ttu-id="4d819-119">Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="4d819-119">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="4d819-120">Agregue este elemento a dicha sección `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="4d819-120">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="EventLog"
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="APPLICATION_NAME"/>
    ```

    <span data-ttu-id="4d819-121">Reemplace `APPLICATION_NAME` por el nombre de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d819-121">Replace `APPLICATION_NAME` with the name of your application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4d819-122">Normalmente, una aplicación escribe solo errores en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="4d819-122">Typically, an application writes only errors to the event log.</span></span> <span data-ttu-id="4d819-123">Para obtener información sobre el filtrado de la salida del registro, consulte [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="4d819-123">For information on filtering log output, see [Walkthrough: Filtering My.Application.Log Output](walkthrough-filtering-my-application-log-output.md).</span></span>

## <a name="to-write-event-information-to-the-event-log"></a><span data-ttu-id="4d819-124">Para escribir información de eventos en el registro de eventos</span><span class="sxs-lookup"><span data-stu-id="4d819-124">To write event information to the event log</span></span>

<span data-ttu-id="4d819-125">Use el método `My.Application.Log.WriteEntry` o `My.Application.Log.WriteException` para escribir información en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="4d819-125">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the event log.</span></span> <span data-ttu-id="4d819-126">Para obtener más información, vea [Cómo: Escribir mensajes de registro](how-to-write-log-messages.md) y [Cómo: Registrar excepciones](how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="4d819-126">For more information, see [How to: Write Log Messages](how-to-write-log-messages.md) and [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

<span data-ttu-id="4d819-127">Después de configurar el agente de escucha de registro de eventos para un ensamblado, este recibe todos los mensajes que `My.Application.Log` escribe desde ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4d819-127">After you configure the event log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d819-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d819-128">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="4d819-129">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="4d819-129">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="4d819-130">Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="4d819-130">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
- [<span data-ttu-id="4d819-131">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="4d819-131">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
