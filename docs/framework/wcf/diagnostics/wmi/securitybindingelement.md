---
title: SecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b567c173c5a04421bce57585d96b8b45144c5625
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="securitybindingelement"></a><span data-ttu-id="2f894-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2f894-102">SecurityBindingElement</span></span>
<span data-ttu-id="2f894-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2f894-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f894-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f894-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="2f894-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2f894-105">Methods</span></span>  
 <span data-ttu-id="2f894-106">La clase SecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="2f894-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2f894-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2f894-107">Properties</span></span>  
 <span data-ttu-id="2f894-108">La clase SecurityBindingElement posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2f894-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="2f894-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="2f894-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="2f894-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2f894-110">Data type: string</span></span>  
  
 <span data-ttu-id="2f894-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2f894-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f894-112">Especifica los algoritmos que se van a utilizar con la clase.</span><span class="sxs-lookup"><span data-stu-id="2f894-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="2f894-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="2f894-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="2f894-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="2f894-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="2f894-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2f894-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f894-116">Valor booleano que especifica si cada mensaje contiene una marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="2f894-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="2f894-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="2f894-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="2f894-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2f894-118">Data type: string</span></span>  
  
 <span data-ttu-id="2f894-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2f894-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f894-120">Origen de la entropía utilizada para crear claves.</span><span class="sxs-lookup"><span data-stu-id="2f894-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="2f894-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="2f894-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="2f894-122">Tipo de datos: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="2f894-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="2f894-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2f894-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f894-124">Las propiedades de seguridad específicas del enlace del servicio local.</span><span class="sxs-lookup"><span data-stu-id="2f894-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="2f894-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="2f894-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="2f894-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2f894-126">Data type: string</span></span>  
  
 <span data-ttu-id="2f894-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2f894-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f894-128">Versión utilizada para la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f894-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="2f894-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="2f894-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="2f894-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2f894-130">Data type: string</span></span>  
  
 <span data-ttu-id="2f894-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2f894-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2f894-132">Orden de los elementos en el encabezado de seguridad de este enlace.</span><span class="sxs-lookup"><span data-stu-id="2f894-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f894-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f894-133">Requirements</span></span>  
  
|<span data-ttu-id="2f894-134">MOF</span><span class="sxs-lookup"><span data-stu-id="2f894-134">MOF</span></span>|<span data-ttu-id="2f894-135">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2f894-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2f894-136">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="2f894-136">Namespace</span></span>|<span data-ttu-id="2f894-137">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2f894-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f894-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f894-138">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>
