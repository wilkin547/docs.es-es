---
title: '&lt;add&gt; de &lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 63f8e678b81838a25664180888e9e7a8eabd043d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722028"
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="c4ddd-102">&lt;add&gt; de &lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="c4ddd-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="c4ddd-103">Especifica una cuenta de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="c4ddd-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="c4ddd-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="c4ddd-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4ddd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4ddd-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4ddd-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c4ddd-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c4ddd-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c4ddd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4ddd-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4ddd-108">Attributes</span></span>  
  
|<span data-ttu-id="c4ddd-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c4ddd-109">Attribute</span></span>|<span data-ttu-id="c4ddd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4ddd-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4ddd-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="c4ddd-111">securityIdentifier</span></span>|<span data-ttu-id="c4ddd-112">Una cadena que  especifica un identificador único usado para reconocer una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c4ddd-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="c4ddd-113">Los valores predeterminados son LocalSystem, Administradores, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="c4ddd-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4ddd-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c4ddd-114">Child Elements</span></span>  
 <span data-ttu-id="c4ddd-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c4ddd-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4ddd-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4ddd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c4ddd-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4ddd-117">Element</span></span>|<span data-ttu-id="c4ddd-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4ddd-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4ddd-119">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="c4ddd-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="c4ddd-120">Una colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedidos acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="c4ddd-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c4ddd-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4ddd-121">Example</span></span>  
 <span data-ttu-id="c4ddd-122">El ejemplo de configuración siguiente agrega los cinco identificadores predeterminados para cuentas de usuario a esta colección.</span><span class="sxs-lookup"><span data-stu-id="c4ddd-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c4ddd-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4ddd-123">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
