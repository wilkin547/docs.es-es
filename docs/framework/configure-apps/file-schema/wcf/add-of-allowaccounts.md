---
title: '&lt;add&gt; de &lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 2230b8d22a14c3df5eb3aa10872246febce015e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349696"
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="0db3c-102">&lt;add&gt; de &lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="0db3c-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="0db3c-103">Especifica una cuenta de usuario para los procesos que alojan servicios WCF y se concede el acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="0db3c-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="0db3c-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="0db3c-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0db3c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0db3c-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0db3c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0db3c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0db3c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0db3c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0db3c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0db3c-108">Attributes</span></span>  
  
|<span data-ttu-id="0db3c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0db3c-109">Attribute</span></span>|<span data-ttu-id="0db3c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0db3c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0db3c-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="0db3c-111">securityIdentifier</span></span>|<span data-ttu-id="0db3c-112">Una cadena que  especifica un identificador único usado para reconocer una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0db3c-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="0db3c-113">Los valores predeterminados son LocalSystem, Administradores, NS, LS e IIS_USRS.</span><span class="sxs-lookup"><span data-stu-id="0db3c-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0db3c-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0db3c-114">Child Elements</span></span>  
 <span data-ttu-id="0db3c-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0db3c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0db3c-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0db3c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0db3c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="0db3c-117">Element</span></span>|<span data-ttu-id="0db3c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0db3c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0db3c-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="0db3c-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="0db3c-120">Una colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que alojan servicios WCF y se conceden el acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="0db3c-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0db3c-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0db3c-121">Example</span></span>  
 <span data-ttu-id="0db3c-122">El ejemplo de configuración siguiente agrega los cinco identificadores predeterminados para cuentas de usuario a esta colección.</span><span class="sxs-lookup"><span data-stu-id="0db3c-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0db3c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0db3c-123">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
