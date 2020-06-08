---
title: 'Cómo: Escribir información de eventos en un archivo de texto'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs [Visual Studio], writing event information
- text files [Visual Basic], writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
ms.openlocfilehash: 6e83f8450ca7be8a2dcd5ff43eab3dd2ec0d2f1b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410067"
---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a><span data-ttu-id="812d3-102">Cómo: Escribir información de eventos en un archivo de texto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="812d3-102">How to: Write Event Information to a Text File (Visual Basic)</span></span>

<span data-ttu-id="812d3-103">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="812d3-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="812d3-104">En este ejemplo se muestra cómo usar el método `My.Application.Log.WriteEntry` para registrar información de seguimiento en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="812d3-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information to a log file.</span></span>

### <a name="to-add-and-configure-the-file-log-listener"></a><span data-ttu-id="812d3-105">Para agregar y configurar el agente de escucha de registro de archivos</span><span class="sxs-lookup"><span data-stu-id="812d3-105">To add and configure the file log listener</span></span>

1. <span data-ttu-id="812d3-106">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="812d3-106">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

     <span data-ttu-id="812d3-107">\- o -</span><span class="sxs-lookup"><span data-stu-id="812d3-107">\- or -</span></span>

     <span data-ttu-id="812d3-108">Si no hay ningún archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="812d3-108">If there is no app.config file:</span></span>

    1. <span data-ttu-id="812d3-109">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="812d3-109">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="812d3-110">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="812d3-110">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="812d3-111">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="812d3-111">Click **Add**.</span></span>

2. <span data-ttu-id="812d3-112">Ubique la sección `<listeners>` en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="812d3-112">Locate the `<listeners>` section in the application configuration file.</span></span>

     <span data-ttu-id="812d3-113">Encontrará la sección \<listeners> en la sección \<source> con el atributo de nombre "DefaultSource", que está anidada bajo la sección \<system.diagnostics> , anidada bajo la sección de nivel superior \<configuration> .</span><span class="sxs-lookup"><span data-stu-id="812d3-113">You will find the \<listeners> section in the \<source> section with the name attribute "DefaultSource", which is nested under the \<system.diagnostics> section, which is nested under the top-level \<configuration> section.</span></span>

3. <span data-ttu-id="812d3-114">Agregue este elemento a dicha sección `<listeners>` :</span><span class="sxs-lookup"><span data-stu-id="812d3-114">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="FileLogListener" />
    ```

4. <span data-ttu-id="812d3-115">Busque la sección `<sharedListeners>`, en la sección `<system.diagnostics>`, anidada en la sección de nivel superior `<configuration>`.</span><span class="sxs-lookup"><span data-stu-id="812d3-115">Locate the `<sharedListeners>` section in the `<system.diagnostics>` section, nested under the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="812d3-116">Agregue este elemento a dicha sección `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="812d3-116">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="FileLogListener"
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,
              PublicKeyToken=b03f5f7f11d50a3a"
        initializeData="FileLogListenerWriter"
        location="Custom"
        customlocation="c:\temp\" />
    ```

     <span data-ttu-id="812d3-117">Cambie el valor del atributo `customlocation` al directorio de registro.</span><span class="sxs-lookup"><span data-stu-id="812d3-117">Change the value of the `customlocation` attribute to the log directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="812d3-118">Para establecer el valor de una propiedad de agente de escucha, use un atributo que tenga el mismo nombre que la propiedad, con todas las letras del nombre en minúscula.</span><span class="sxs-lookup"><span data-stu-id="812d3-118">To set the value of a listener property, use an attribute that has the same name as the property, with all letters in the name lowercase.</span></span> <span data-ttu-id="812d3-119">Por ejemplo, los atributos `location` y `customlocation` establecen los valores de las propiedades <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> y <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A>.</span><span class="sxs-lookup"><span data-stu-id="812d3-119">For example, the `location` and `customlocation` attributes set the values of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> and <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> properties.</span></span>

### <a name="to-write-event-information-to-the-file-log"></a><span data-ttu-id="812d3-120">Para escribir información de eventos en el registro de archivo</span><span class="sxs-lookup"><span data-stu-id="812d3-120">To write event information to the file log</span></span>

<span data-ttu-id="812d3-121">Use el método `My.Application.Log.WriteEntry` o `My.Application.Log.WriteException` para escribir información en el registro de archivo.</span><span class="sxs-lookup"><span data-stu-id="812d3-121">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the file log.</span></span> <span data-ttu-id="812d3-122">Para obtener más información, vea [Cómo: Escribir mensajes de registro](how-to-write-log-messages.md) y [Cómo: Registrar excepciones](how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="812d3-122">For more information, see [How to: Write Log Messages](how-to-write-log-messages.md) and [How to: Log Exceptions](how-to-log-exceptions.md).</span></span>

<span data-ttu-id="812d3-123">Después de configurar el agente de escucha de registro de archivo para un ensamblado, este recibe todos los mensajes que `My.Application.Log` escribe desde ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="812d3-123">After you configure the file log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="812d3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="812d3-124">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="812d3-125">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="812d3-125">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="812d3-126">Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="812d3-126">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)
