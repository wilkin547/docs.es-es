---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772107"
---
# <a name="servicecredentials"></a><span data-ttu-id="e4fe2-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="e4fe2-102">ServiceCredentials</span></span>
<span data-ttu-id="e4fe2-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="e4fe2-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4fe2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4fe2-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e4fe2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e4fe2-105">Methods</span></span>  
 <span data-ttu-id="e4fe2-106">La clase ServiceCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e4fe2-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e4fe2-107">Properties</span></span>  
 <span data-ttu-id="e4fe2-108">La clase ServiceCredentials posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="e4fe2-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="e4fe2-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="e4fe2-109">ClientCertificate</span></span>  
 <span data-ttu-id="e4fe2-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e4fe2-110">Data type: string</span></span>  
  
 <span data-ttu-id="e4fe2-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e4fe2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4fe2-112">La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="e4fe2-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="e4fe2-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="e4fe2-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e4fe2-114">Data type: string</span></span>  
  
 <span data-ttu-id="e4fe2-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e4fe2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4fe2-116">Los valores actuales de autenticación de token emitido para este servicio.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="e4fe2-117">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="e4fe2-117">Peer</span></span>  
 <span data-ttu-id="e4fe2-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e4fe2-118">Data type: string</span></span>  
  
 <span data-ttu-id="e4fe2-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e4fe2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4fe2-120">La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los puntos de conexión de transporte del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="e4fe2-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="e4fe2-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="e4fe2-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e4fe2-122">Data type: string</span></span>  
  
 <span data-ttu-id="e4fe2-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e4fe2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4fe2-124">Especifica los valores de conversación seguros actuales.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="e4fe2-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="e4fe2-125">ServiceCertificate</span></span>  
 <span data-ttu-id="e4fe2-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e4fe2-126">Data type: string</span></span>  
  
 <span data-ttu-id="e4fe2-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e4fe2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4fe2-128">El certificado asociado a este servicio.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="e4fe2-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="e4fe2-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="e4fe2-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e4fe2-130">Data type: string</span></span>  
  
 <span data-ttu-id="e4fe2-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e4fe2-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4fe2-132">Los valores de nombre de usuario/contraseña para este servicio.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="e4fe2-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="e4fe2-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="e4fe2-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e4fe2-134">Data type: string</span></span>  
  
 <span data-ttu-id="e4fe2-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="e4fe2-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e4fe2-136">Los valores de autenticación de Windows para este servicio.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4fe2-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4fe2-137">Requirements</span></span>  
  
|<span data-ttu-id="e4fe2-138">MOF</span><span class="sxs-lookup"><span data-stu-id="e4fe2-138">MOF</span></span>|<span data-ttu-id="e4fe2-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e4fe2-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e4fe2-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e4fe2-140">Namespace</span></span>|<span data-ttu-id="e4fe2-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e4fe2-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4fe2-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4fe2-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
