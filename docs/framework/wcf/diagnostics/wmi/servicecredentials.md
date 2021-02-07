---
description: 'Más información acerca de: ServiceCredentials'
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: bfd025a8f671a3c5aea537059cde0e751cfa9bb9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715553"
---
# <a name="servicecredentials"></a><span data-ttu-id="11bde-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="11bde-103">ServiceCredentials</span></span>

<span data-ttu-id="11bde-104">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="11bde-104">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11bde-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11bde-105">Syntax</span></span>  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="11bde-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="11bde-106">Methods</span></span>  

 <span data-ttu-id="11bde-107">La clase ServiceCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="11bde-107">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="11bde-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="11bde-108">Properties</span></span>  

 <span data-ttu-id="11bde-109">La clase ServiceCredentials posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="11bde-109">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="11bde-110">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="11bde-110">ClientCertificate</span></span>  

 <span data-ttu-id="11bde-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="11bde-111">Data type: string</span></span>  
  
 <span data-ttu-id="11bde-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="11bde-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11bde-113">La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.</span><span class="sxs-lookup"><span data-stu-id="11bde-113">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="11bde-114">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="11bde-114">IssuedTokenAuthentication</span></span>  

 <span data-ttu-id="11bde-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="11bde-115">Data type: string</span></span>  
  
 <span data-ttu-id="11bde-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="11bde-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11bde-117">Los valores actuales de autenticación de token emitido para este servicio.</span><span class="sxs-lookup"><span data-stu-id="11bde-117">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="11bde-118">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="11bde-118">Peer</span></span>  

 <span data-ttu-id="11bde-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="11bde-119">Data type: string</span></span>  
  
 <span data-ttu-id="11bde-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="11bde-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11bde-121">La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los puntos de conexión de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="11bde-121">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="11bde-122">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="11bde-122">SecureConversationAuthentication</span></span>  

 <span data-ttu-id="11bde-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="11bde-123">Data type: string</span></span>  
  
 <span data-ttu-id="11bde-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="11bde-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11bde-125">Especifica los valores de conversación seguros actuales.</span><span class="sxs-lookup"><span data-stu-id="11bde-125">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="11bde-126">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="11bde-126">ServiceCertificate</span></span>  

 <span data-ttu-id="11bde-127">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="11bde-127">Data type: string</span></span>  
  
 <span data-ttu-id="11bde-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="11bde-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11bde-129">El certificado asociado a este servicio.</span><span class="sxs-lookup"><span data-stu-id="11bde-129">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="11bde-130">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="11bde-130">UserNameAuthentication</span></span>  

 <span data-ttu-id="11bde-131">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="11bde-131">Data type: string</span></span>  
  
 <span data-ttu-id="11bde-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="11bde-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11bde-133">Los valores de nombre de usuario/contraseña para este servicio.</span><span class="sxs-lookup"><span data-stu-id="11bde-133">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="11bde-134">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="11bde-134">WindowsAuthentication</span></span>  

 <span data-ttu-id="11bde-135">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="11bde-135">Data type: string</span></span>  
  
 <span data-ttu-id="11bde-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="11bde-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="11bde-137">Los valores de autenticación de Windows para este servicio.</span><span class="sxs-lookup"><span data-stu-id="11bde-137">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11bde-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11bde-138">Requirements</span></span>  
  
|<span data-ttu-id="11bde-139">MOF</span><span class="sxs-lookup"><span data-stu-id="11bde-139">MOF</span></span>|<span data-ttu-id="11bde-140">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="11bde-140">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="11bde-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="11bde-141">Namespace</span></span>|<span data-ttu-id="11bde-142">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="11bde-142">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11bde-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="11bde-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
