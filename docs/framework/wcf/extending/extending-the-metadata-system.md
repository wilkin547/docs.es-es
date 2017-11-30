---
title: "Extensión del sistema de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cab59f5ddebdcc1e50921d5540d411e32b562341
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="3c3cb-102">Extensión del sistema de metadatos</span><span class="sxs-lookup"><span data-stu-id="3c3cb-102">Extending the Metadata System</span></span>
<span data-ttu-id="3c3cb-103">El sistema de metadatos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es un grupo de clases e interfaces que representan los metadatos requeridos para implementar las aplicaciones basadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="3c3cb-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="3c3cb-104">Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="3c3cb-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c3cb-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3c3cb-105">In This Section</span></span>  
 [<span data-ttu-id="3c3cb-106">Exportación de metadatos personalizados para una extensión de WCF</span><span class="sxs-lookup"><span data-stu-id="3c3cb-106">Exporting Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="3c3cb-107">Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> para incrustar las aserciones de directiva personalizadas en documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="3c3cb-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="3c3cb-108">Importar metadatos personalizados para una extensión de WCF</span><span class="sxs-lookup"><span data-stu-id="3c3cb-108">Importing Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="3c3cb-109">Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> para leer y contestar las aserciones de directiva personalizadas en documentos WSDL.</span><span class="sxs-lookup"><span data-stu-id="3c3cb-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="3c3cb-110">Publicación y recuperación de metadatos a través de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="3c3cb-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="3c3cb-111">Describe cómo intercambiar los metadatos sobre los enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="3c3cb-111">Describes how to exchange metadata over custom bindings.</span></span>
