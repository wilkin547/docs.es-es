---
title: '&lt;add&gt; de &lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09ab06bb94249e79743335da1a360f6b668b1d86
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="62b10-102">&lt;add&gt; de &lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="62b10-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="62b10-103">Especifica una cuenta de usuario para los procesos que hospedan los servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="62b10-103">Specifies a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="62b10-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="62b10-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62b10-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62b10-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62b10-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="62b10-106">Attributes and Elements</span></span>  
 <span data-ttu-id="62b10-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="62b10-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62b10-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="62b10-108">Attributes</span></span>  
  
|<span data-ttu-id="62b10-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="62b10-109">Attribute</span></span>|<span data-ttu-id="62b10-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="62b10-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62b10-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="62b10-111">securityIdentifier</span></span>|<span data-ttu-id="62b10-112">Una cadena que  especifica un identificador único usado para reconocer una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="62b10-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="62b10-113">Los valores predeterminados son LocalSystem, Administradores, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="62b10-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62b10-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="62b10-114">Child Elements</span></span>  
 <span data-ttu-id="62b10-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="62b10-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62b10-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="62b10-116">Parent Elements</span></span>  
  
|<span data-ttu-id="62b10-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="62b10-117">Element</span></span>|<span data-ttu-id="62b10-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="62b10-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62b10-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="62b10-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="62b10-120">Una colección de elementos de configuración que contiene un atributo `securityIdentifier` que especifica cuentas de usuario para los procesos que hospedan servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y se concede el acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="62b10-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="62b10-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62b10-121">Example</span></span>  
 <span data-ttu-id="62b10-122">El ejemplo de configuración siguiente agrega los cinco identificadores predeterminados para cuentas de usuario a esta colección.</span><span class="sxs-lookup"><span data-stu-id="62b10-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62b10-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="62b10-123">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
