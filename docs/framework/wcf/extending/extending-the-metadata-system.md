---
title: Extensión del sistema de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7113120a3cde6b4e6a7eb1d329da625e25996952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272988"
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="c0ac2-102">Extensión del sistema de metadatos</span><span class="sxs-lookup"><span data-stu-id="c0ac2-102">Extending the Metadata System</span></span>

<span data-ttu-id="c0ac2-103">El sistema de metadatos de Windows Communication Foundation (WCF) es un grupo de clases e interfaces que representan los metadatos necesarios para implementar aplicaciones basadas en servicio.</span><span class="sxs-lookup"><span data-stu-id="c0ac2-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="c0ac2-104">Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="c0ac2-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0ac2-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c0ac2-105">In This Section</span></span>  

 [<span data-ttu-id="c0ac2-106">Exportación de metadatos personalizados para una extensión WCF</span><span class="sxs-lookup"><span data-stu-id="c0ac2-106">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="c0ac2-107">Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> para incrustar las aserciones de directiva personalizadas en documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="c0ac2-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="c0ac2-108">Importación de  metadatos personalizados para una extensión de WCF</span><span class="sxs-lookup"><span data-stu-id="c0ac2-108">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="c0ac2-109">Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> para leer y contestar las aserciones de directiva personalizadas en documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="c0ac2-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="c0ac2-110">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="c0ac2-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="c0ac2-111">Describe cómo intercambiar los metadatos sobre los enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="c0ac2-111">Describes how to exchange metadata over custom bindings.</span></span>
