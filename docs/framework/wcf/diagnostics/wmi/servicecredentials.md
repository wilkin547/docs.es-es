---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956986"
---
# <a name="servicecredentials"></a><span data-ttu-id="641e9-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="641e9-102">ServiceCredentials</span></span>
<span data-ttu-id="641e9-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="641e9-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="641e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="641e9-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="641e9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="641e9-105">Methods</span></span>  
 <span data-ttu-id="641e9-106">La clase ServiceCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="641e9-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="641e9-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="641e9-107">Properties</span></span>  
 <span data-ttu-id="641e9-108">La clase ServiceCredentials posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="641e9-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="641e9-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="641e9-109">ClientCertificate</span></span>  
 <span data-ttu-id="641e9-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="641e9-110">Data type: string</span></span>  
  
 <span data-ttu-id="641e9-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="641e9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641e9-112">La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.</span><span class="sxs-lookup"><span data-stu-id="641e9-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="641e9-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="641e9-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="641e9-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="641e9-114">Data type: string</span></span>  
  
 <span data-ttu-id="641e9-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="641e9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641e9-116">Los valores actuales de autenticación de token emitido para este servicio.</span><span class="sxs-lookup"><span data-stu-id="641e9-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="641e9-117">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="641e9-117">Peer</span></span>  
 <span data-ttu-id="641e9-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="641e9-118">Data type: string</span></span>  
  
 <span data-ttu-id="641e9-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="641e9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641e9-120">La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los puntos de conexión de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="641e9-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="641e9-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="641e9-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="641e9-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="641e9-122">Data type: string</span></span>  
  
 <span data-ttu-id="641e9-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="641e9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641e9-124">Especifica los valores de conversación seguros actuales.</span><span class="sxs-lookup"><span data-stu-id="641e9-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="641e9-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="641e9-125">ServiceCertificate</span></span>  
 <span data-ttu-id="641e9-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="641e9-126">Data type: string</span></span>  
  
 <span data-ttu-id="641e9-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="641e9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641e9-128">El certificado asociado a este servicio.</span><span class="sxs-lookup"><span data-stu-id="641e9-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="641e9-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="641e9-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="641e9-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="641e9-130">Data type: string</span></span>  
  
 <span data-ttu-id="641e9-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="641e9-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641e9-132">Los valores de nombre de usuario/contraseña para este servicio.</span><span class="sxs-lookup"><span data-stu-id="641e9-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="641e9-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="641e9-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="641e9-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="641e9-134">Data type: string</span></span>  
  
 <span data-ttu-id="641e9-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="641e9-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="641e9-136">Los valores de autenticación de Windows para este servicio.</span><span class="sxs-lookup"><span data-stu-id="641e9-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="641e9-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="641e9-137">Requirements</span></span>  
  
|<span data-ttu-id="641e9-138">MOF</span><span class="sxs-lookup"><span data-stu-id="641e9-138">MOF</span></span>|<span data-ttu-id="641e9-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="641e9-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="641e9-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="641e9-140">Namespace</span></span>|<span data-ttu-id="641e9-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="641e9-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="641e9-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="641e9-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
