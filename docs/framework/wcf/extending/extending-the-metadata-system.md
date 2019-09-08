---
title: Extensión del sistema de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: d3ce7e1a228e6303be1009c7b72f4e889b40c536
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795720"
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="a3280-102">Extensión del sistema de metadatos</span><span class="sxs-lookup"><span data-stu-id="a3280-102">Extending the Metadata System</span></span>
<span data-ttu-id="a3280-103">El sistema de metadatos de Windows Communication Foundation (WCF) es un grupo de clases e interfaces que representan los metadatos necesarios para implementar aplicaciones basadas en servicio.</span><span class="sxs-lookup"><span data-stu-id="a3280-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="a3280-104">Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="a3280-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3280-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a3280-105">In This Section</span></span>  
 [<span data-ttu-id="a3280-106">Exportación de metadatos personalizados para una extensión WCF</span><span class="sxs-lookup"><span data-stu-id="a3280-106">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="a3280-107">Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> para incrustar las aserciones de directiva personalizadas en documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="a3280-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="a3280-108">Importación de metadatos personalizados para una extensión WCF</span><span class="sxs-lookup"><span data-stu-id="a3280-108">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="a3280-109">Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> para leer y contestar las aserciones de directiva personalizadas en documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="a3280-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="a3280-110">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="a3280-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="a3280-111">Describe cómo intercambiar los metadatos sobre los enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="a3280-111">Describes how to exchange metadata over custom bindings.</span></span>
