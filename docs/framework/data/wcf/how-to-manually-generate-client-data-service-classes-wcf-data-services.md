---
description: 'Más información acerca de cómo: generar manualmente clases del servicio de datos del cliente (Servicios de datos de WCF)'
title: 'Cómo: Generar manualmente clases del servicio de datos cliente (Servicios de datos de WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 6fe878e1177055540a29fb84252eddaa4d97e536
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765209"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="dd8cf-103">Cómo: Generar manualmente clases del servicio de datos cliente (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="dd8cf-103">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="dd8cf-104">Servicios de datos de WCF se integra con Visual Studio para permitir la generación automática de las clases del servicio de datos del cliente cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para agregar una referencia a un servicio de datos en un proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-104">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="dd8cf-105">Para obtener más información, vea [Cómo: agregar una referencia de servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dd8cf-105">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="dd8cf-106">También puede generar manualmente las mismas clases del servicio de datos del cliente mediante la herramienta de generación de código `DataSvcUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-106">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="dd8cf-107">Esta herramienta, que se incluye con Servicios de datos de WCF, genera clases de .NET Framework a partir de la definición del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-107">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="dd8cf-108">También se puede usar para generar clases del servicio de datos a partir del archivo de modelo conceptual (.csdl) y del archivo .edmx que representa un modelo de Entity Framework en un proyecto Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-108">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="dd8cf-109">El ejemplo usado en este tema crea clases del servicio de datos del cliente basadas en el servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-109">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="dd8cf-110">Este servicio se crea cuando se completa la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dd8cf-110">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="dd8cf-111">Algunos ejemplos de este tema requieren el archivo de modelo conceptual para el modelo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-111">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="dd8cf-112">Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="dd8cf-112">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="dd8cf-113">Algunos ejemplos de este tema requieren el archivo de modelo conceptual .edmx para el modelo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-113">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="dd8cf-114">Para obtener más información, vea [información general sobre el archivo. edmx](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="dd8cf-114">For more information, see [.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="dd8cf-115">Para generar clases de C# que admitan el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="dd8cf-115">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="dd8cf-116">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="dd8cf-116">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="dd8cf-117">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-117">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="dd8cf-118">Para generar clases Visual Basic que admitan el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="dd8cf-118">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="dd8cf-119">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="dd8cf-119">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="dd8cf-120">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-120">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="dd8cf-121">Para generar clases de C# basadas en el URI de servicio</span><span class="sxs-lookup"><span data-stu-id="dd8cf-121">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="dd8cf-122">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="dd8cf-122">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="dd8cf-123">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-123">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="dd8cf-124">Para generar clases de Visual Basic basadas en el URI de servicio</span><span class="sxs-lookup"><span data-stu-id="dd8cf-124">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="dd8cf-125">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="dd8cf-125">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="dd8cf-126">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="dd8cf-126">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="dd8cf-127">Para generar clases de C# basadas en el archivo de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="dd8cf-127">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="dd8cf-128">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="dd8cf-128">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="dd8cf-129">Para generar clases de Visual Basic basadas en el archivo de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="dd8cf-129">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="dd8cf-130">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="dd8cf-130">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="dd8cf-131">Para generar clases de C# basadas en el archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="dd8cf-131">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="dd8cf-132">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="dd8cf-132">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="dd8cf-133">Para generar clases de Visual Basic basadas en el archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="dd8cf-133">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="dd8cf-134">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="dd8cf-134">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="dd8cf-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd8cf-135">See also</span></span>

- [<span data-ttu-id="dd8cf-136">Generar la biblioteca cliente del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="dd8cf-136">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="dd8cf-137">Procedimiento para agregar una referencia a un servicio de datos</span><span class="sxs-lookup"><span data-stu-id="dd8cf-137">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="dd8cf-138">Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="dd8cf-138">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](wcf-data-service-client-utility-datasvcutil-exe.md)
