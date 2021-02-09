---
description: 'Más información acerca de: Procedimiento: para escribir información de eventos en un archivo de texto (Visual Basic)'
title: Procedimiento para escribir información de eventos en un archivo de texto
ms.date: 07/20/2015
helpviewer_keywords:
- event logs [Visual Studio], writing event information
- text files [Visual Basic], writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
ms.openlocfilehash: eb6fab9976c010080c0cffa37edd4f790dc73956
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775141"
---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a><span data-ttu-id="b235d-103">Cómo: Escribir información de eventos en un archivo de texto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b235d-103">How to: Write Event Information to a Text File (Visual Basic)</span></span>

<span data-ttu-id="b235d-104">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b235d-104">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="b235d-105">En este ejemplo se muestra cómo usar el método `My.Application.Log.WriteEntry` para registrar información de seguimiento en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="b235d-105">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information to a log file.</span></span>

### <a name="to-add-and-configure-the-file-log-listener"></a><span data-ttu-id="b235d-106">Para agregar y configurar el agente de escucha de registro de archivos</span><span class="sxs-lookup"><span data-stu-id="b235d-106">To add and configure the file log listener</span></span>

1. <span data-ttu-id="b235d-107">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b235d-107">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="b235d-108">\- o -</span><span class="sxs-lookup"><span data-stu-id="b235d-108">\- or -</span></span>

     <span data-ttu-id="b235d-109">Si no hay ningún archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="b235d-109">If there is no app.config file:</span></span>

    1. <span data-ttu-id="b235d-110">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b235d-110">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="b235d-111">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="b235d-111">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="b235d-112">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b235d-112">Click **Add**.</span></span>

2. <span data-ttu-id="b235d-113">Ubique la sección `<listeners>` en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b235d-113">Locate the `<listeners>` section in the application configuration file.</span></span>

     <span data-ttu-id="b235d-114">Encontrará la sección \<listeners> en la sección \<source> con el atributo de nombre "DefaultSource", que está anidada bajo la sección \<system.diagnostics> , anidada bajo la sección de nivel superior \<configuration> .</span><span class="sxs-lookup"><span data-stu-id="b235d-114">You will find the \<listeners> section in the \<source> section with the name attribute "DefaultSource", which is nested under the \<system.diagnostics> section, which is nested under the top-level \<configuration> section.</span></span>

3. <span data-ttu-id="b235d-115">Agregue este elemento a dicha sección `<listeners>` :</span><span class="sxs-lookup"><span data-stu-id="b235d-115">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="FileLogListener" />
    ```

4. <span data-ttu-id="b235d-116">Busque la sección `<sharedListeners>`, en la sección `<system.diagnostics>`, anidada en la sección de nivel superior `<configuration>`.</span><span class="sxs-lookup"><span data-stu-id="b235d-116">Locate the `<sharedListeners>` section in the `<system.diagnostics>` section, nested under the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="b235d-117">Agregue este elemento a dicha sección `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="b235d-117">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="FileLogListener"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
              PublicKeyToken=b03f5f7f11d50a3a"
        initializeData="FileLogListenerWriter"
        location="Custom"
        customlocation="c:\temp\" />
    ```

     <span data-ttu-id="b235d-118">Cambie el valor del atributo `customlocation` al directorio de registro.</span><span class="sxs-lookup"><span data-stu-id="b235d-118">Change the value of the `customlocation` attribute to the log directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b235d-119">Para establecer el valor de una propiedad de agente de escucha, use un atributo que tenga el mismo nombre que la propiedad, con todas las letras del nombre en minúscula.</span><span class="sxs-lookup"><span data-stu-id="b235d-119">To set the value of a listener property, use an attribute that has the same name as the property, with all letters in the name lowercase.</span></span> <span data-ttu-id="b235d-120">Por ejemplo, los atributos `location` y `customlocation` establecen los valores de las propiedades <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> y <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A>.</span><span class="sxs-lookup"><span data-stu-id="b235d-120">For example, the `location` and `customlocation` attributes set the values of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> and <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> properties.</span></span>

### <a name="to-write-event-information-to-the-file-log"></a><span data-ttu-id="b235d-121">Para escribir información de eventos en el registro de archivo</span><span class="sxs-lookup"><span data-stu-id="b235d-121">To write event information to the file log</span></span>

<span data-ttu-id="b235d-122">Use el método `My.Application.Log.WriteEntry` o `My.Application.Log.WriteException` para escribir información en el registro de archivo.</span><span class="sxs-lookup"><span data-stu-id="b235d-122">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the file log.</span></span> <span data-ttu-id="b235d-123">Para obtener más información, vea [Cómo: Escribir mensajes de registro](how-to-write-log-messages.md) y [Cómo: Registrar excepciones](how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="b235d-123">For more information, see [How to: Write Log Messages](how-to-write-log-messages.md) and [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

<span data-ttu-id="b235d-124">Después de configurar el agente de escucha de registro de archivo para un ensamblado, este recibe todos los mensajes que `My.Application.Log` escribe desde ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b235d-124">After you configure the file log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="b235d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b235d-125">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="b235d-126">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b235d-126">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="b235d-127">Cómo: Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="b235d-127">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
