---
title: <add> de <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: cd4b9fd02eee2de1d0e8be185ffb69c0eae1cd58
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181731"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="02bf2-102">\<add> de \<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="02bf2-102">\<add> of \<allowAccounts></span></span>

<span data-ttu-id="02bf2-103">Especifica una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="02bf2-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="02bf2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02bf2-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02bf2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02bf2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="02bf2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02bf2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02bf2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="02bf2-107">Attributes</span></span>  
  
|<span data-ttu-id="02bf2-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="02bf2-108">Attribute</span></span>|<span data-ttu-id="02bf2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="02bf2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02bf2-110">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="02bf2-110">securityIdentifier</span></span>|<span data-ttu-id="02bf2-111">Una cadena que  especifica un identificador único usado para reconocer una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="02bf2-111">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="02bf2-112">Los valores predeterminados son LocalSystem, Administradores, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="02bf2-112">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02bf2-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02bf2-113">Child Elements</span></span>  

 <span data-ttu-id="02bf2-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02bf2-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02bf2-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02bf2-115">Parent Elements</span></span>  
  
|<span data-ttu-id="02bf2-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="02bf2-116">Element</span></span>|<span data-ttu-id="02bf2-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="02bf2-117">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="02bf2-118">Colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="02bf2-118">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02bf2-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02bf2-119">Example</span></span>  

 <span data-ttu-id="02bf2-120">El ejemplo de configuración siguiente agrega los cinco identificadores predeterminados para cuentas de usuario a esta colección.</span><span class="sxs-lookup"><span data-stu-id="02bf2-120">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02bf2-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02bf2-121">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
