---
title: <add> de <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398378"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="77692-102">\<add> de \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="77692-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="77692-103">Especifica una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="77692-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="77692-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77692-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77692-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="77692-105">Attributes and Elements</span></span>  
 <span data-ttu-id="77692-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="77692-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77692-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="77692-107">Attributes</span></span>  
  
|<span data-ttu-id="77692-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="77692-108">Attribute</span></span>|<span data-ttu-id="77692-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="77692-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77692-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="77692-110">securityIdentifier</span></span>|<span data-ttu-id="77692-111">Una cadena que  especifica un identificador único usado para reconocer una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="77692-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="77692-112">Los valores predeterminados son LocalSystem, Administradores, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="77692-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77692-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="77692-113">Child Elements</span></span>  
 <span data-ttu-id="77692-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="77692-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77692-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="77692-115">Parent Elements</span></span>  
  
|<span data-ttu-id="77692-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="77692-116">Element</span></span>|<span data-ttu-id="77692-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="77692-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="77692-118">Colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="77692-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="77692-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77692-119">Example</span></span>  
 <span data-ttu-id="77692-120">El ejemplo de configuración siguiente agrega los cinco identificadores predeterminados para cuentas de usuario a esta colección.</span><span class="sxs-lookup"><span data-stu-id="77692-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="77692-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77692-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
