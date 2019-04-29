---
title: <system.serviceModel.activation>
ms.date: 03/30/2017
ms.assetid: c0cae85f-56cb-4030-8807-6f96edff8d2d
ms.openlocfilehash: b29f7173b4d75ec9adff37449d3d56266f01a03c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759166"
---
# <a name="systemservicemodelactivation"></a><span data-ttu-id="05d5b-102">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="05d5b-102">\<system.serviceModel.activation></span></span>
<span data-ttu-id="05d5b-103">Esta sección de configuración representa la configuración de la herramienta SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="05d5b-103">This configuration section represents the configuration settings for the SMSvcHost.exe tool.</span></span> <span data-ttu-id="05d5b-104">Los elementos de configuración se pueden configurar en el archivo SMSvcHost.exe.config.</span><span class="sxs-lookup"><span data-stu-id="05d5b-104">The configuration elements can be configured in the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="05d5b-105">Específicamente, incluye todos los valores de equipo que se deben configurar.</span><span class="sxs-lookup"><span data-stu-id="05d5b-105">Specifically, it includes all machine-wide settings that must be configured.</span></span>  
  
## <a name="sample-configuration-file"></a><span data-ttu-id="05d5b-106">Archivo de configuración del ejemplo</span><span class="sxs-lookup"><span data-stu-id="05d5b-106">Sample Configuration File</span></span>  
 <span data-ttu-id="05d5b-107">A continuación, se muestra un archivo de configuración del ejemplo (SMSvcHost.exe.config), que es utilizado por el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="05d5b-107">The following is a sample configuration file (SMSvcHost.exe.config), which is used by the listener process SMSvcHost.exe.</span></span>  
  
```xml  
<configuration>
  <runtime>
    <gcConcurrent enabled="false" />
  </runtime>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="10"
             maxPendingAccepts="2"
             maxPendingConnections="100"
             receiveTimeout="00:00:10"
             teredoEnabled="false">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
    <net.pipe maxConnectionsPendingDispatch="100"
              maxPendingAccepts="2"
              receiveTimeout="00:00:10">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
    <diagnostics performanceCountersEnabled="true" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="05d5b-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="05d5b-108">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration>
