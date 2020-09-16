---
title: 'Cómo: Generar manualmente clases del servicio de datos cliente (Servicios de datos de WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 31bf2e543bf20199fbeeaa8d00f808650092ff00
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546964"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="ebefe-102">Cómo: Generar manualmente clases del servicio de datos cliente (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="ebefe-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="ebefe-103">WCF Data Services se integra con Visual Studio para permitir la generación automática de las clases del servicio de datos del cliente cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para agregar una referencia a un servicio de datos en un proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ebefe-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="ebefe-104">Para obtener más información, vea [Cómo: agregar una referencia de servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ebefe-104">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="ebefe-105">También puede generar manualmente las mismas clases del servicio de datos del cliente mediante la herramienta de generación de código `DataSvcUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="ebefe-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="ebefe-106">Esta herramienta, que se incluye con WCF Data Services, genera clases de .NET Framework a partir de la definición del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="ebefe-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="ebefe-107">También se puede usar para generar clases del servicio de datos a partir del archivo de modelo conceptual (.csdl) y del archivo .edmx que representa un modelo de Entity Framework en un proyecto Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ebefe-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="ebefe-108">El ejemplo usado en este tema crea clases del servicio de datos del cliente basadas en el servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ebefe-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="ebefe-109">Este servicio se crea cuando se completa la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ebefe-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="ebefe-110">Algunos ejemplos de este tema requieren el archivo de modelo conceptual para el modelo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ebefe-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="ebefe-111">Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="ebefe-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="ebefe-112">Algunos ejemplos de este tema requieren el archivo de modelo conceptual .edmx para el modelo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ebefe-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="ebefe-113">Para obtener más información, vea [información general sobre el archivo. edmx](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ebefe-113">For more information, see [.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="ebefe-114">Para generar clases de C# que admitan el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ebefe-114">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="ebefe-115">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ebefe-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="ebefe-116">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ebefe-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="ebefe-117">Para generar clases Visual Basic que admitan el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ebefe-117">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="ebefe-118">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ebefe-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="ebefe-119">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ebefe-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="ebefe-120">Para generar clases de C# basadas en el URI de servicio</span><span class="sxs-lookup"><span data-stu-id="ebefe-120">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="ebefe-121">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ebefe-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="ebefe-122">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ebefe-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="ebefe-123">Para generar clases de Visual Basic basadas en el URI de servicio</span><span class="sxs-lookup"><span data-stu-id="ebefe-123">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="ebefe-124">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ebefe-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="ebefe-125">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="ebefe-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="ebefe-126">Para generar clases de C# basadas en el archivo de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="ebefe-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="ebefe-127">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ebefe-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="ebefe-128">Para generar clases de Visual Basic basadas en el archivo de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="ebefe-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="ebefe-129">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ebefe-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="ebefe-130">Para generar clases de C# basadas en el archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="ebefe-130">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="ebefe-131">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ebefe-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="ebefe-132">Para generar clases de Visual Basic basadas en el archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="ebefe-132">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="ebefe-133">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="ebefe-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="ebefe-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebefe-134">See also</span></span>

- [<span data-ttu-id="ebefe-135">Generar la biblioteca cliente del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="ebefe-135">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="ebefe-136">Procedimiento para agregar una referencia a un servicio de datos</span><span class="sxs-lookup"><span data-stu-id="ebefe-136">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="ebefe-137">Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="ebefe-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](wcf-data-service-client-utility-datasvcutil-exe.md)
