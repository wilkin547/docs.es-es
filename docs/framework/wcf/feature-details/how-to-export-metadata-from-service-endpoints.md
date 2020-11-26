---
title: Procedimiento para exportar metadatos desde puntos de conexión de servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b6c4dfd0-f270-43ec-961a-e16eb6af2f2c
ms.openlocfilehash: c253358b68cf18a23bab4d12d4ad760874103bff
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246412"
---
# <a name="how-to-export-metadata-from-service-endpoints"></a><span data-ttu-id="25d15-102">Procedimiento para exportar metadatos desde puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="25d15-102">How to: Export Metadata from Service Endpoints</span></span>

<span data-ttu-id="25d15-103">En este tema se explica cómo exportar los metadatos desde los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="25d15-103">This topic explains how to export metadata from service endpoints.</span></span>  
  
### <a name="to-export-metadata-from-service-endpoints"></a><span data-ttu-id="25d15-104">Exportar metadatos desde puntos de conexión de servicio</span><span class="sxs-lookup"><span data-stu-id="25d15-104">To export metadata from service endpoints</span></span>  
  
1. <span data-ttu-id="25d15-105">Cree un nuevo Proyecto App de Consola de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="25d15-105">Create a new Visual Studio Console App Project.</span></span> <span data-ttu-id="25d15-106">Agregue el código que se muestra en los pasos siguientes en el archivo Program.cs generado dentro del método main().</span><span class="sxs-lookup"><span data-stu-id="25d15-106">Add the code shown in the following steps in the generated Program.cs file within the main() method.</span></span>  
  
2. <span data-ttu-id="25d15-107">Creará un control <xref:System.ServiceModel.Description.WsdlExporter>.</span><span class="sxs-lookup"><span data-stu-id="25d15-107">Create a <xref:System.ServiceModel.Description.WsdlExporter>.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#1)]
     [!code-vb[S_UEWsdlExporter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#1)]  
  
3. <span data-ttu-id="25d15-108">Establezca la propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> en uno de los valores de enumeración desde <xref:System.ServiceModel.Description.PolicyVersion>.</span><span class="sxs-lookup"><span data-stu-id="25d15-108">Set the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to one of the values from the <xref:System.ServiceModel.Description.PolicyVersion> enumeration.</span></span> <span data-ttu-id="25d15-109">Este ejemplo establece el valor en <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> que corresponde a WS-Policy 1.5.</span><span class="sxs-lookup"><span data-stu-id="25d15-109">This sample sets the value to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> which corresponds to WS-Policy 1.5.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#2)]
     [!code-vb[S_UEWsdlExporter#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#2)]  
  
4. <span data-ttu-id="25d15-110">Cree una matriz de objetos <xref:System.ServiceModel.Description.ServiceEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="25d15-110">Create an array of <xref:System.ServiceModel.Description.ServiceEndpoint> objects.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#3)]
     [!code-vb[S_UEWsdlExporter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#3)]  
  
5. <span data-ttu-id="25d15-111">Exporte los metadatos para cada punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="25d15-111">Export metadata for each service endpoint.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#4)]
     [!code-vb[S_UEWsdlExporter#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#4)]  
  
6. <span data-ttu-id="25d15-112">Compruebe para asegurarse de que no se produjo ningún error durante el proceso de exportación y recupere los metadatos.</span><span class="sxs-lookup"><span data-stu-id="25d15-112">Check to make sure no errors occurred during the export process and retrieve the metadata.</span></span>  
  
     [!code-csharp[S_UEWsdlExporter#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#5)]
     [!code-vb[S_UEWsdlExporter#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#5)]  
  
7. <span data-ttu-id="25d15-113">Ahora puede utilizar los metadatos, de manera que puede escribirlos en un archivo llamando al método <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29>.</span><span class="sxs-lookup"><span data-stu-id="25d15-113">You can now use the metadata, such as write it to a file by calling the <xref:System.ServiceModel.Description.MetadataSet.WriteTo%28System.Xml.XmlWriter%29> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25d15-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25d15-114">Example</span></span>  

 <span data-ttu-id="25d15-115">A continuación, se muestra una lista de código completa para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="25d15-115">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[S_UEWsdlExporter#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_uewsdlexporter/cs/program.cs#0)]
 [!code-vb[S_UEWsdlExporter#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_uewsdlexporter/vb/program.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="25d15-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="25d15-116">Compiling the Code</span></span>  

 <span data-ttu-id="25d15-117">Al compilar Program.cs, haga referencia a System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="25d15-117">When compiling Program.cs reference System.ServiceModel.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d15-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="25d15-118">See also</span></span>

- [<span data-ttu-id="25d15-119">Información general de la arquitectura de metadatos</span><span class="sxs-lookup"><span data-stu-id="25d15-119">Metadata Architecture Overview</span></span>](metadata-architecture-overview.md)
- [<span data-ttu-id="25d15-120">Utilización de los metadatos</span><span class="sxs-lookup"><span data-stu-id="25d15-120">Using Metadata</span></span>](using-metadata.md)
- [<span data-ttu-id="25d15-121">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="25d15-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
