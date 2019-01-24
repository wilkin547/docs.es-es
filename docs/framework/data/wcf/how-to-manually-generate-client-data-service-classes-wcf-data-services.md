---
title: Procedimiento Generar manualmente clases de servicio de datos de cliente (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: c95ad9371854257059861b7d1e48c7afbc957ea1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613235"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="ccdbe-102">Procedimiento Generar manualmente clases de servicio de datos de cliente (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ccdbe-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="ccdbe-103">WCF Data Services se integra con Visual Studio que le permite generar automáticamente clases de servicio de datos de cliente cuando se usa el **Add Service Reference** cuadro de diálogo para agregar una referencia a un servicio de datos en un proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="ccdbe-104">Para obtener más información, vea [Cómo: Agregar una referencia de servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ccdbe-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="ccdbe-105">También puede generar manualmente las mismas clases del servicio de datos del cliente mediante la herramienta de generación de código `DataSvcUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="ccdbe-106">Esta herramienta, que se incluye con WCF Data Services, genera clases de .NET Framework de la definición de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="ccdbe-107">También se puede usar para generar clases del servicio de datos a partir del archivo de modelo conceptual (.csdl) y del archivo .edmx que representa un modelo de Entity Framework en un proyecto Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="ccdbe-108">El ejemplo usado en este tema crea clases del servicio de datos del cliente basadas en el servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="ccdbe-109">Este servicio se crea al completar el [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ccdbe-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="ccdbe-110">Algunos ejemplos de este tema requieren el archivo de modelo conceptual para el modelo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="ccdbe-111">Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="ccdbe-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="ccdbe-112">Algunos ejemplos de este tema requieren el archivo de modelo conceptual .edmx para el modelo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="ccdbe-113">Para obtener más información, consulte [información general del archivo .edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span><span class="sxs-lookup"><span data-stu-id="ccdbe-113">For more information, see [.edmx File Overview](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="ccdbe-114">Para generar clases de C# que admitan el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ccdbe-114">To generate C# classes that support data binding</span></span>

-   <span data-ttu-id="ccdbe-115">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ccdbe-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="ccdbe-116">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="ccdbe-117">Para generar clases Visual Basic que admitan el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ccdbe-117">To generate Visual Basic classes that support data binding</span></span>

-   <span data-ttu-id="ccdbe-118">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ccdbe-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="ccdbe-119">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="ccdbe-120">Para generar clases de C# basadas en el URI de servicio</span><span class="sxs-lookup"><span data-stu-id="ccdbe-120">To generate C# classes based on the service URI</span></span>

-   <span data-ttu-id="ccdbe-121">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ccdbe-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="ccdbe-122">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="ccdbe-123">Para generar clases de Visual Basic basadas en el URI de servicio</span><span class="sxs-lookup"><span data-stu-id="ccdbe-123">To generate Visual Basic classes based on the service URI</span></span>

-   <span data-ttu-id="ccdbe-124">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ccdbe-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="ccdbe-125">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ccdbe-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="ccdbe-126">Para generar clases de C# basadas en el archivo de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="ccdbe-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

-   <span data-ttu-id="ccdbe-127">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ccdbe-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="ccdbe-128">Para generar clases de Visual Basic basadas en el archivo de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="ccdbe-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

-   <span data-ttu-id="ccdbe-129">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ccdbe-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="ccdbe-130">Para generar clases de C# basadas en el archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="ccdbe-130">To generate C# classes based on the .edmx file</span></span>

-   <span data-ttu-id="ccdbe-131">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ccdbe-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="ccdbe-132">Para generar clases de Visual Basic basadas en el archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="ccdbe-132">To generate Visual Basic classes based on the .edmx file</span></span>

-   <span data-ttu-id="ccdbe-133">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ccdbe-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="ccdbe-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccdbe-134">See also</span></span>

- [<span data-ttu-id="ccdbe-135">Generar la biblioteca cliente del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="ccdbe-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="ccdbe-136">Cómo: Agregar una referencia de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="ccdbe-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="ccdbe-137">Utilidad del cliente de servicio de datos de WCF (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="ccdbe-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)