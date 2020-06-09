---
title: Procedimiento para exportar metadatos desde puntos de conexión de servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
ms.openlocfilehash: 58e86e5566775048e081bfb4ac217a7747b98a35
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579415"
---
# <a name="how-to-export-metadata-from-service-endpoints"></a><span data-ttu-id="61a04-102">Procedimiento para exportar metadatos desde puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="61a04-102">How to: Export Metadata from Service Endpoints</span></span>
<span data-ttu-id="61a04-103">En este tema se explica cómo exportar los metadatos desde los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="61a04-103">This topic explains how to export metadata from service endpoints.</span></span>  
  
### <a name="to-export-metadata-from-service-endpoints"></a><span data-ttu-id="61a04-104">Exportar metadatos desde puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="61a04-104">To export metadata from service endpoints</span></span>  
  
1. <span data-ttu-id="61a04-105">Cree un nuevo Proyecto App de Consola de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="61a04-105">Create a new Visual Studio Console App Project.</span></span> <span data-ttu-id="61a04-106">Agregue el código que se muestra en los pasos siguientes en el archivo Program.cs generado dentro del método main().</span><span class="sxs-lookup"><span data-stu-id="61a04-106">Add the code shown in the following steps in the generated Program.cs file within the main() method.</span></span>  
  
2. <span data-ttu-id="61a04-107">Creará un control <xref:System.ServiceModel.Description.WsdlExporter>.</span><span class="sxs-lookup"><span data-stu-id="61a04-107">Create a <xref:System.ServiceModel.Description.WsdlExporter>.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3. <span data-ttu-id="61a04-108">Establezca la propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> en uno de los valores de enumeración desde <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="61a04-108">Set the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to one of the values from the <xref:System.ServiceModel.Description.PolicyVersion> enumeration.</span></span> <span data-ttu-id="61a04-109">Este ejemplo establece el valor en <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> que corresponde a WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="61a04-109">This sample sets the value to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> which corresponds to WS-Policy 1.5.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4. <span data-ttu-id="61a04-110">Cree una matriz de objetos <xref:System.ServiceModel.Description.ServiceEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="61a04-110">Create an array of <xref:System.ServiceModel.Description.ServiceEndpoint> objects.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5. <span data-ttu-id="61a04-111">Exporte los metadatos para cada punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="61a04-111">Export metadata for each service endpoint.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6. <span data-ttu-id="61a04-112">Compruebe para asegurarse de que no se produjo ningún error durante el proceso de exportación y recupere los metadatos.</span><span class="sxs-lookup"><span data-stu-id="61a04-112">Check to make sure no errors occurred during the export process and retrieve the metadata.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7. <span data-ttu-id="61a04-113">Ahora puede utilizar los metadatos, de manera que puede escribirlos en un archivo llamando al método <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29>.</span><span class="sxs-lookup"><span data-stu-id="61a04-113">You can now use the metadata, such as write it to a file by calling the <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61a04-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61a04-114">Example</span></span>  
 <span data-ttu-id="61a04-115">A continuación, se muestra una lista de código completa para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="61a04-115">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="61a04-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="61a04-116">Compiling the Code</span></span>  
 <span data-ttu-id="61a04-117">Al compilar Program.cs, haga referencia a System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="61a04-117">When compiling Program.cs reference System.ServiceModel.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a04-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="61a04-118">See also</span></span>

- [<span data-ttu-id="61a04-119">Información general de la arquitectura de metadatos</span><span class="sxs-lookup"><span data-stu-id="61a04-119">Metadata Architecture Overview</span></span>](metadata-architecture-overview.md)
- [<span data-ttu-id="61a04-120">Utilización de los metadatos</span><span class="sxs-lookup"><span data-stu-id="61a04-120">Using Metadata</span></span>](using-metadata.md)
- [<span data-ttu-id="61a04-121">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="61a04-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
