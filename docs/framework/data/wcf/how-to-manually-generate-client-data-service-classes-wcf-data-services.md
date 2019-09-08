---
title: Procedimiento Generar manualmente clases del servicio de datos del cliente (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 106f1cedb33c0c1b333df0b9f2b8c2a70d458a0d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790427"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="555ff-102">Procedimiento Generar manualmente clases del servicio de datos del cliente (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="555ff-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="555ff-103">WCF Data Services se integra con Visual Studio para permitir la generación automática de las clases del servicio de datos del cliente cuando se usa el cuadro de diálogo **Agregar referencia de servicio** para agregar una referencia a un servicio de datos en un proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="555ff-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="555ff-104">Para obtener más información, vea [Cómo: Agregue una referencia](how-to-add-a-data-service-reference-wcf-data-services.md)de servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="555ff-104">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="555ff-105">También puede generar manualmente las mismas clases del servicio de datos del cliente mediante la herramienta de generación de código `DataSvcUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="555ff-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="555ff-106">Esta herramienta, que se incluye con WCF Data Services, genera clases de .NET Framework a partir de la definición del servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="555ff-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="555ff-107">También se puede usar para generar clases del servicio de datos a partir del archivo de modelo conceptual (.csdl) y del archivo .edmx que representa un modelo de Entity Framework en un proyecto Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="555ff-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="555ff-108">El ejemplo usado en este tema crea clases del servicio de datos del cliente basadas en el servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="555ff-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="555ff-109">Este servicio se crea cuando se completa la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="555ff-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="555ff-110">Algunos ejemplos de este tema requieren el archivo de modelo conceptual para el modelo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="555ff-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="555ff-111">Para obtener más información, consulte [Cómo Use EdmGen. exe para generar los archivos](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)de asignación y de modelo.</span><span class="sxs-lookup"><span data-stu-id="555ff-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="555ff-112">Algunos ejemplos de este tema requieren el archivo de modelo conceptual .edmx para el modelo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="555ff-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="555ff-113">Para obtener más información, vea [información general sobre el archivo. edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="555ff-113">For more information, see [.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="555ff-114">Para generar clases de C# que admitan el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="555ff-114">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="555ff-115">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="555ff-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="555ff-116">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="555ff-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="555ff-117">Para generar clases Visual Basic que admitan el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="555ff-117">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="555ff-118">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="555ff-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="555ff-119">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="555ff-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="555ff-120">Para generar clases de C# basadas en el URI de servicio</span><span class="sxs-lookup"><span data-stu-id="555ff-120">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="555ff-121">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="555ff-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="555ff-122">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="555ff-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="555ff-123">Para generar clases de Visual Basic basadas en el URI de servicio</span><span class="sxs-lookup"><span data-stu-id="555ff-123">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="555ff-124">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="555ff-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="555ff-125">Debe reemplazar el valor proporcionado para el parámetro `/uri:` con el URI de la instancia del servicio de datos de ejemplo de Northwind.</span><span class="sxs-lookup"><span data-stu-id="555ff-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="555ff-126">Para generar clases de C# basadas en el archivo de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="555ff-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="555ff-127">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="555ff-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="555ff-128">Para generar clases de Visual Basic basadas en el archivo de modelo conceptual (CSDL)</span><span class="sxs-lookup"><span data-stu-id="555ff-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="555ff-129">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="555ff-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="555ff-130">Para generar clases de C# basadas en el archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="555ff-130">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="555ff-131">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="555ff-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="555ff-132">Para generar clases de Visual Basic basadas en el archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="555ff-132">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="555ff-133">En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:</span><span class="sxs-lookup"><span data-stu-id="555ff-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="555ff-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="555ff-134">See also</span></span>

- [<span data-ttu-id="555ff-135">Generar la biblioteca cliente del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="555ff-135">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="555ff-136">Cómo: Agregar una referencia de servicio de datos</span><span class="sxs-lookup"><span data-stu-id="555ff-136">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="555ff-137">Utilidad del cliente de servicio de datos de WCF (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="555ff-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](wcf-data-service-client-utility-datasvcutil-exe.md)
