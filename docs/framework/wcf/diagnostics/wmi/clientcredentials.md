---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c3adc675bb6c1e9011459a88fd7dc8e8cf63a880
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963985"
---
# <a name="clientcredentials"></a><span data-ttu-id="8dd70-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="8dd70-102">ClientCredentials</span></span>
<span data-ttu-id="8dd70-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="8dd70-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dd70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dd70-104">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8dd70-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8dd70-105">Methods</span></span>  
 <span data-ttu-id="8dd70-106">La clase ClientCredentials no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="8dd70-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8dd70-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8dd70-107">Properties</span></span>  
 <span data-ttu-id="8dd70-108">La clase ClientCredentials tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="8dd70-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="8dd70-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="8dd70-109">ClientCertificate</span></span>  
 <span data-ttu-id="8dd70-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dd70-110">Data type: string</span></span>  
  
 <span data-ttu-id="8dd70-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8dd70-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dd70-112">El certificado X.509 que utiliza el cliente para autenticarse en el servicio.</span><span class="sxs-lookup"><span data-stu-id="8dd70-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="8dd70-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="8dd70-113">HttpDigest</span></span>  
 <span data-ttu-id="8dd70-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dd70-114">Data type: string</span></span>  
  
 <span data-ttu-id="8dd70-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8dd70-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dd70-116">La credencial de resumen Http Digest actual.</span><span class="sxs-lookup"><span data-stu-id="8dd70-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="8dd70-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="8dd70-117">IssuedToken</span></span>  
 <span data-ttu-id="8dd70-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dd70-118">Data type: string</span></span>  
  
 <span data-ttu-id="8dd70-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8dd70-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dd70-120">La dirección y el enlace del extremo utilizados para contactar con el servicio de tokens de seguridad local.</span><span class="sxs-lookup"><span data-stu-id="8dd70-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="8dd70-121">Del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="8dd70-121">Peer</span></span>  
 <span data-ttu-id="8dd70-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dd70-122">Data type: string</span></span>  
  
 <span data-ttu-id="8dd70-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8dd70-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dd70-124">Las credenciales que el nodo del mismo nivel utiliza para autenticarse a otros nodos de la malla.</span><span class="sxs-lookup"><span data-stu-id="8dd70-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="8dd70-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="8dd70-125">ServiceCertificate</span></span>  
 <span data-ttu-id="8dd70-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dd70-126">Data type: string</span></span>  
  
 <span data-ttu-id="8dd70-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8dd70-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dd70-128">El certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="8dd70-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="8dd70-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="8dd70-129">SupportInteractive</span></span>  
 <span data-ttu-id="8dd70-130">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="8dd70-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="8dd70-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8dd70-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dd70-132">Un valor booleano que especifica si la credencial admite negociación interactiva.</span><span class="sxs-lookup"><span data-stu-id="8dd70-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="8dd70-133">UserName</span><span class="sxs-lookup"><span data-stu-id="8dd70-133">UserName</span></span>  
 <span data-ttu-id="8dd70-134">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dd70-134">Data type: string</span></span>  
  
 <span data-ttu-id="8dd70-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8dd70-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dd70-136">El nombre de usuario y la contraseña que el cliente utiliza para autenticarse al servicio.</span><span class="sxs-lookup"><span data-stu-id="8dd70-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="8dd70-137">Windows</span><span class="sxs-lookup"><span data-stu-id="8dd70-137">Windows</span></span>  
 <span data-ttu-id="8dd70-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="8dd70-138">Data type: string</span></span>  
  
 <span data-ttu-id="8dd70-139">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="8dd70-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8dd70-140">Las credenciales de Windows que el cliente utiliza para autenticarse al servicio.</span><span class="sxs-lookup"><span data-stu-id="8dd70-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dd70-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dd70-141">Requirements</span></span>  
  
|<span data-ttu-id="8dd70-142">MOF</span><span class="sxs-lookup"><span data-stu-id="8dd70-142">MOF</span></span>|<span data-ttu-id="8dd70-143">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8dd70-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8dd70-144">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="8dd70-144">Namespace</span></span>|<span data-ttu-id="8dd70-145">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8dd70-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8dd70-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dd70-146">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>
