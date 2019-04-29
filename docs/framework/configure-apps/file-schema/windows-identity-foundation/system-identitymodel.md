---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 2f0040fb7084b9d53adbd1a114f1cfc62d58e5a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793762"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="b8d57-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b8d57-102">\<system.identityModel></span></span>
<span data-ttu-id="b8d57-103">Proporciona la configuración para habilitar las opciones de Windows Identity Foundation (WIF) en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b8d57-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="b8d57-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b8d57-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8d57-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8d57-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8d57-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b8d57-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b8d57-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b8d57-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8d57-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b8d57-108">Attributes</span></span>  
 <span data-ttu-id="b8d57-109">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b8d57-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8d57-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b8d57-110">Child Elements</span></span>  
  
|<span data-ttu-id="b8d57-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8d57-111">Element</span></span>|<span data-ttu-id="b8d57-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8d57-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8d57-113">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b8d57-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="b8d57-114">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="b8d57-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8d57-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b8d57-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b8d57-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b8d57-116">Element</span></span>|<span data-ttu-id="b8d57-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8d57-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="b8d57-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8d57-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8d57-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8d57-119">Remarks</span></span>  
 <span data-ttu-id="b8d57-120">Agregar un `<system.identityModel>` sección al archivo de configuración para configurar un servicio o aplicación para que use Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="b8d57-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="b8d57-121">El `<system.identityModel>` elemento representado por la <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> clase.</span><span class="sxs-lookup"><span data-stu-id="b8d57-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8d57-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8d57-122">Example</span></span>  
 <span data-ttu-id="b8d57-123">El ejemplo siguiente muestra cómo agregar un `<system.identityModel>` sección a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b8d57-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="b8d57-124">En primer lugar debe agregar la declaración de espacio de nombres y la sección de configuración bajo el `<configSections>` elemento.</span><span class="sxs-lookup"><span data-stu-id="b8d57-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="b8d57-125">A continuación, puede agregar el `<system.IdentityModel>` elemento al archivo de configuración para especificar una o varias configuraciones de identidad.</span><span class="sxs-lookup"><span data-stu-id="b8d57-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8d57-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8d57-126">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
