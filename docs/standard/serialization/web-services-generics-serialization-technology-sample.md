---
title: Ejemplo de Web Services Generics Serialization Technology
ms.date: 03/30/2017
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
ms.openlocfilehash: 467bfe1fd9eb8a0222385c34cb29a90df00dc937
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960748"
---
# <a name="web-services-generics-serialization-technology-sample"></a><span data-ttu-id="0c723-102">Ejemplo de Web Services Generics Serialization Technology</span><span class="sxs-lookup"><span data-stu-id="0c723-102">Web Services Generics Serialization Technology Sample</span></span>
[<span data-ttu-id="0c723-103">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c723-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 <span data-ttu-id="0c723-104">Este ejemplo muestra cómo utilizar y controlar la serialización de genéricos en servicios Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0c723-104">This sample shows how to use and control the serialization of generics in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="0c723-105">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c723-105">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="0c723-106">Abra Visual Studio y seleccione **Nuevo sitio web** en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="0c723-106">Open Visual Studio and select **New Web Site** from the **File** menu.</span></span>  
  
2. <span data-ttu-id="0c723-107">En el panel izquierdo del cuadro de diálogo **Nuevo sitio web**, seleccione su lenguaje de programación deseado y, a continuación, en el panel derecho, seleccione **Servicio Web ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="0c723-107">In the **New Web Site** dialog, select from the left pane your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3. <span data-ttu-id="0c723-108">Haga clic en **Examinar** y desplácese hasta el subdirectorio del \CS\GenericsService.</span><span class="sxs-lookup"><span data-stu-id="0c723-108">Click **Browse** and navigate to the \CS\GenericsService subdirectory.</span></span>  
  
4. <span data-ttu-id="0c723-109">Seleccione Service.asmx para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0c723-109">Select Service.asmx to open the file in Visual Studio.</span></span>  
  
5. <span data-ttu-id="0c723-110">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="0c723-110">On the **Build** menu, click **Build Solution**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c723-111">Los primeros cinco pasos en esta lista son opcionales.</span><span class="sxs-lookup"><span data-stu-id="0c723-111">The first five steps in this list are optional.</span></span> <span data-ttu-id="0c723-112">El runtime de .NET Framework generará automáticamente el servicio Web la primera vez que se solicita el servicio.</span><span class="sxs-lookup"><span data-stu-id="0c723-112">The .NET Framework runtime will automatically generate the Web service the first time the service is requested.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c723-113">Los siguientes pasos son obligatorios para generar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c723-113">The following steps are required to build the sample.</span></span>  
  
1. <span data-ttu-id="0c723-114">Abra el Explorador de archivos y navegue hasta el subdirectorio \CS.</span><span class="sxs-lookup"><span data-stu-id="0c723-114">Open File Explorer and navigate to the \CS subdirectory.</span></span>  
  
2. <span data-ttu-id="0c723-115">Haga clic con el botón secundario en el icono del subdirectorio GenericsService y seleccione **Compartir y seguridad**.</span><span class="sxs-lookup"><span data-stu-id="0c723-115">Right-click the icon for the GenericsService subdirectory, and select **Sharing and Security**.</span></span>  
  
3. <span data-ttu-id="0c723-116">En la pestaña **Uso compartido de web**, seleccione **Compartir esta carpeta**.</span><span class="sxs-lookup"><span data-stu-id="0c723-116">In the **Web Sharing** tab, select **Share this Folder**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0c723-117">Tome nota del nombre del directorio virtual que aparece en la lista en el panel **Alias**, porque necesitará para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c723-117">Take note of the virtual directory name that is listed in the **Aliases** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-build-the-sample-using-internet-information-services"></a><span data-ttu-id="0c723-118">Para generar el ejemplo mediante Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="0c723-118">To build the sample using Internet Information Services</span></span>  
  
1. <span data-ttu-id="0c723-119">Abra el complemento de administración de **Internet Information Services** y expanda **Sitios web**.</span><span class="sxs-lookup"><span data-stu-id="0c723-119">Open the **Internet Information Services** management snap-in and expand **Web Sites**.</span></span>  
  
2. <span data-ttu-id="0c723-120">Haga clic en **Sitio web predeterminado** y seleccione **Nuevo**, **Directorio virtual** para crear el **Asistente para crear un directorio virtual**.</span><span class="sxs-lookup"><span data-stu-id="0c723-120">Left-click **Default Web Site**, select **New**, and then select **Virtual Directory?** to create the **Virtual Directory Creation Wizard**.</span></span>  
  
3. <span data-ttu-id="0c723-121">Haga clic en **Siguiente**, escriba el alias público para su directorio virtual y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0c723-121">Click **Next**, enter the public alias for your virtual directory, and click **Next**.</span></span>  
  
4. <span data-ttu-id="0c723-122">Escriba la ruta de acceso al directorio donde guardó el ejemplo (normalmente el subdirectorio del \CS\GenericsService) y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0c723-122">Enter the path to the directory where you saved the sample (normally the \CS\GenericsService subdirectory) and click **Next**.</span></span> <span data-ttu-id="0c723-123">Haga clic en **Siguiente** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="0c723-123">Click **Next** to finish the wizard.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0c723-124">Tome nota del nombre del directorio virtual que aparece en la lista en el panel **Alias**, porque necesitará para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c723-124">Take note of the virtual directory name that is listed in the **Alias** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="0c723-125">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c723-125">To run the sample</span></span>  
  
1. <span data-ttu-id="0c723-126">Abra una ventana del explorador y seleccione su barra de direcciones.</span><span class="sxs-lookup"><span data-stu-id="0c723-126">Open a browser window and select its address bar.</span></span>  
  
2. <span data-ttu-id="0c723-127">Escriba `http://localhost/[virtual directory]/Service.asmx`, donde `[virtual directory]` representa el directorio virtual que ha creado al compilar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c723-127">Type `http://localhost/[virtual directory]/Service.asmx`, where `[virtual directory]` represents the virtual directory you created when you built the sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c723-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c723-128">Remarks</span></span>  
 <span data-ttu-id="0c723-129">En el ejemplo se muestra una página ASP.NET predeterminada que contiene los vínculos a la definición del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="0c723-129">The sample displays a default ASP.NET page that contains links to the definition of the Web Service.</span></span> <span data-ttu-id="0c723-130">Puede personalizar la presentación además de modificar el código fuente del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="0c723-130">You can customize the display in addition to modifying the source code for the Web service.</span></span> <span data-ttu-id="0c723-131">Para obtener más información, vea [Building XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)) (Crear clientes de servicios Web XML).</span><span class="sxs-lookup"><span data-stu-id="0c723-131">For more information, see [Building XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c723-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c723-132">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Web.Services>
- <xref:System.Xml.Serialization>
- [<span data-ttu-id="0c723-133">Serialización</span><span class="sxs-lookup"><span data-stu-id="0c723-133">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- <span data-ttu-id="0c723-134">[Servicios Web XML creados con ASP.NET y clientes de servicio Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0c723-134">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
