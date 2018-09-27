---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
author: BrucePerlerMS
ms.openlocfilehash: 19c65b3028ad63b8a78205d00f44cc32322648d5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396853"
---
# <a name="securitybindingelement"></a><span data-ttu-id="99533-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="99533-102">SecurityBindingElement</span></span>
<span data-ttu-id="99533-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="99533-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99533-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99533-104">Syntax</span></span>  
  
```  
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="99533-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="99533-105">Methods</span></span>  
 <span data-ttu-id="99533-106">La clase SecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="99533-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="99533-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="99533-107">Properties</span></span>  
 <span data-ttu-id="99533-108">La clase SecurityBindingElement posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="99533-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="99533-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="99533-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="99533-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="99533-110">Data type: string</span></span>  
  
 <span data-ttu-id="99533-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="99533-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99533-112">Especifica los algoritmos que se van a utilizar con la clase.</span><span class="sxs-lookup"><span data-stu-id="99533-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="99533-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="99533-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="99533-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="99533-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="99533-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="99533-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99533-116">Valor booleano que especifica si cada mensaje contiene una marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="99533-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="99533-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="99533-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="99533-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="99533-118">Data type: string</span></span>  
  
 <span data-ttu-id="99533-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="99533-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99533-120">Origen de la entropía utilizada para crear claves.</span><span class="sxs-lookup"><span data-stu-id="99533-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="99533-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="99533-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="99533-122">Tipo de datos: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="99533-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="99533-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="99533-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99533-124">Las propiedades de seguridad específicas del enlace del servicio local.</span><span class="sxs-lookup"><span data-stu-id="99533-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="99533-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="99533-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="99533-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="99533-126">Data type: string</span></span>  
  
 <span data-ttu-id="99533-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="99533-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99533-128">Versión utilizada para la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="99533-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="99533-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="99533-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="99533-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="99533-130">Data type: string</span></span>  
  
 <span data-ttu-id="99533-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="99533-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="99533-132">Orden de los elementos en el encabezado de seguridad de este enlace.</span><span class="sxs-lookup"><span data-stu-id="99533-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99533-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99533-133">Requirements</span></span>  
  
|<span data-ttu-id="99533-134">MOF</span><span class="sxs-lookup"><span data-stu-id="99533-134">MOF</span></span>|<span data-ttu-id="99533-135">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="99533-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="99533-136">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="99533-136">Namespace</span></span>|<span data-ttu-id="99533-137">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="99533-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99533-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="99533-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
