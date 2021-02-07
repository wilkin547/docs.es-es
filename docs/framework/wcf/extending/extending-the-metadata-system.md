---
description: Más información acerca de cómo extender el sistema de metadatos
title: Extensión del sistema de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: e8409e29f9dc604ccc6bf399497f3d48f3bcd8f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685561"
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="3f228-103">Extensión del sistema de metadatos</span><span class="sxs-lookup"><span data-stu-id="3f228-103">Extending the Metadata System</span></span>

<span data-ttu-id="3f228-104">El sistema de metadatos de Windows Communication Foundation (WCF) es un grupo de clases e interfaces que representan los metadatos necesarios para implementar aplicaciones basadas en servicio.</span><span class="sxs-lookup"><span data-stu-id="3f228-104">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="3f228-105">Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="3f228-105">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f228-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3f228-106">In This Section</span></span>  

 [<span data-ttu-id="3f228-107">Exportación de metadatos personalizados para una extensión WCF</span><span class="sxs-lookup"><span data-stu-id="3f228-107">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="3f228-108">Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> para incrustar las aserciones de directiva personalizadas en documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="3f228-108">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="3f228-109">Importación de  metadatos personalizados para una extensión de WCF</span><span class="sxs-lookup"><span data-stu-id="3f228-109">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="3f228-110">Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> para leer y contestar las aserciones de directiva personalizadas en documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="3f228-110">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="3f228-111">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="3f228-111">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="3f228-112">Describe cómo intercambiar los metadatos sobre los enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="3f228-112">Describes how to exchange metadata over custom bindings.</span></span>
