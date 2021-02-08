---
description: 'Más información sobre: <add> de <allowAccounts>'
title: <add> de <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 275631c4467a888966e89a2f664b186f989ae101
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782226"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="548e6-103">\<add> de \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="548e6-103">\<add> of \<allowAccounts></span></span>

<span data-ttu-id="548e6-104">Especifica una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="548e6-104">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="548e6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="548e6-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="548e6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="548e6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="548e6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="548e6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="548e6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="548e6-108">Attributes</span></span>  
  
|<span data-ttu-id="548e6-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="548e6-109">Attribute</span></span>|<span data-ttu-id="548e6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="548e6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="548e6-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="548e6-111">securityIdentifier</span></span>|<span data-ttu-id="548e6-112">Una cadena que  especifica un identificador único usado para reconocer una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="548e6-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="548e6-113">Los valores predeterminados son LocalSystem, Administradores, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="548e6-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="548e6-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="548e6-114">Child Elements</span></span>  

 <span data-ttu-id="548e6-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="548e6-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="548e6-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="548e6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="548e6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="548e6-117">Element</span></span>|<span data-ttu-id="548e6-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="548e6-118">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="548e6-119">Colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="548e6-119">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="548e6-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="548e6-120">Example</span></span>  

 <span data-ttu-id="548e6-121">El ejemplo de configuración siguiente agrega los cinco identificadores predeterminados para cuentas de usuario a esta colección.</span><span class="sxs-lookup"><span data-stu-id="548e6-121">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="548e6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="548e6-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
