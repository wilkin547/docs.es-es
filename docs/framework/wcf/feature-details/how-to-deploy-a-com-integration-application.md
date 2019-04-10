---
title: Filtrar para implementar una aplicación de integración de COM+
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: fcf525943e6e453253c6f4d3bcfa8a1a08df6909
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343387"
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="ce59e-102">Filtrar para implementar una aplicación de integración de COM+</span><span class="sxs-lookup"><span data-stu-id="ce59e-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="ce59e-103">Cuando ha escrito una aplicación de integración de COM+, puede que desee implementarla en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="ce59e-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="ce59e-104">En este tema se describe cómo mover una aplicación de integración de COM+ de un equipo a otro.</span><span class="sxs-lookup"><span data-stu-id="ce59e-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="ce59e-105">Mover una aplicación de integración alojada por COM+</span><span class="sxs-lookup"><span data-stu-id="ce59e-105">Moving a COM+ hosted Integration App</span></span>  
  
1. <span data-ttu-id="ce59e-106">Asegúrese de que está instalado WCF en ambos equipos.</span><span class="sxs-lookup"><span data-stu-id="ce59e-106">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="ce59e-107">Exportar la aplicación desde el equipo A.</span><span class="sxs-lookup"><span data-stu-id="ce59e-107">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="ce59e-108">Importar la aplicación en el equipo B.</span><span class="sxs-lookup"><span data-stu-id="ce59e-108">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="ce59e-109">Establezca el directorio raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ce59e-109">Set the Application Root Directory.</span></span> <span data-ttu-id="ce59e-110">Por convención, éste es %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span><span class="sxs-lookup"><span data-stu-id="ce59e-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5. <span data-ttu-id="ce59e-111">Copie los archivos Application.config y Application.manifest del directorio raíz de la aplicación en el equipo A en el directorio raíz de la aplicación en el equipo B.</span><span class="sxs-lookup"><span data-stu-id="ce59e-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6. <span data-ttu-id="ce59e-112">Modifique las direcciones del punto de conexión de servicio en el archivo Application.config en el equipo B para identificar el equipo adecuado.</span><span class="sxs-lookup"><span data-stu-id="ce59e-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="ce59e-113">Por ejemplo, cambie `http://machineA/MyService` a `http://machineB/MyService`.</span><span class="sxs-lookup"><span data-stu-id="ce59e-113">For example, change `http://machineA/MyService` to `http://machineB/MyService`.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="ce59e-114">Mover una aplicación de integración alojada en Web</span><span class="sxs-lookup"><span data-stu-id="ce59e-114">Moving a Web-hosted integration application</span></span>  
  
1. <span data-ttu-id="ce59e-115">Asegúrese de que está instalado WCF en ambos equipos.</span><span class="sxs-lookup"><span data-stu-id="ce59e-115">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="ce59e-116">Exportar la aplicación desde el equipo A.</span><span class="sxs-lookup"><span data-stu-id="ce59e-116">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="ce59e-117">Importar la aplicación en el equipo B.</span><span class="sxs-lookup"><span data-stu-id="ce59e-117">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="ce59e-118">Cree un vroot de IIS en el equipo B.</span><span class="sxs-lookup"><span data-stu-id="ce59e-118">Create an IIS vroot on machine B.</span></span>  
  
5. <span data-ttu-id="ce59e-119">Copie el archivo .svc (componentName.svc) y el archivo Web.config de vroot en el equipo A al vroot recientemente creado en el equipo B.</span><span class="sxs-lookup"><span data-stu-id="ce59e-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce59e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce59e-120">See also</span></span>

- [<span data-ttu-id="ce59e-121">Integración en la información general de las aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="ce59e-121">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)
- [<span data-ttu-id="ce59e-122">Filtrar para configurar los parámetros de los servicios COM+</span><span class="sxs-lookup"><span data-stu-id="ce59e-122">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
- [<span data-ttu-id="ce59e-123">Filtrar para usar la herramienta configuración de modelos de servicio COM+</span><span class="sxs-lookup"><span data-stu-id="ce59e-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
