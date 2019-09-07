---
title: <add> de <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398378"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="d85a4-102">\<Agregar > de \<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="d85a4-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="d85a4-103">Especifica una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="d85a4-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="d85a4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d85a4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d85a4-105">&nbsp;&nbsp;[ **\<System. serviceModel. Activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="d85a4-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="d85a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> net. Pipe**](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="d85a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="d85a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> allowAccounts**](allowaccounts.md)</span><span class="sxs-lookup"><span data-stu-id="d85a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)</span></span>\
<span data-ttu-id="d85a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="d85a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d85a4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d85a4-109">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d85a4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d85a4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d85a4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d85a4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d85a4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d85a4-112">Attributes</span></span>  
  
|<span data-ttu-id="d85a4-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="d85a4-113">Attribute</span></span>|<span data-ttu-id="d85a4-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d85a4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d85a4-115">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="d85a4-115">securityIdentifier</span></span>|<span data-ttu-id="d85a4-116">Una cadena que  especifica un identificador único usado para reconocer una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="d85a4-116">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="d85a4-117">Los valores predeterminados son LocalSystem, Administradores, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="d85a4-117">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d85a4-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d85a4-118">Child Elements</span></span>  
 <span data-ttu-id="d85a4-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d85a4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d85a4-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d85a4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d85a4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d85a4-121">Element</span></span>|<span data-ttu-id="d85a4-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d85a4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d85a4-123">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="d85a4-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="d85a4-124">Colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="d85a4-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d85a4-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d85a4-125">Example</span></span>  
 <span data-ttu-id="d85a4-126">El ejemplo de configuración siguiente agrega los cinco identificadores predeterminados para cuentas de usuario a esta colección.</span><span class="sxs-lookup"><span data-stu-id="d85a4-126">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d85a4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d85a4-127">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
