---
description: 'Más información acerca de: SecurityBindingElement'
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: bc9a519978a9cccccd80a58abb8d109fa9bc9337
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743816"
---
# <a name="securitybindingelement"></a><span data-ttu-id="70cfc-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="70cfc-103">SecurityBindingElement</span></span>

<span data-ttu-id="70cfc-104">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="70cfc-104">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cfc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70cfc-105">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="70cfc-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="70cfc-106">Methods</span></span>  

 <span data-ttu-id="70cfc-107">La clase SecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="70cfc-107">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="70cfc-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="70cfc-108">Properties</span></span>  

 <span data-ttu-id="70cfc-109">La clase SecurityBindingElement posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="70cfc-109">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="70cfc-110">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="70cfc-110">DefaultAlgorithmSuite</span></span>  

 <span data-ttu-id="70cfc-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="70cfc-111">Data type: string</span></span>  
  
 <span data-ttu-id="70cfc-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="70cfc-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70cfc-113">Especifica los algoritmos que se van a utilizar con la clase.</span><span class="sxs-lookup"><span data-stu-id="70cfc-113">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="70cfc-114">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="70cfc-114">IncludeTimestamp</span></span>  

 <span data-ttu-id="70cfc-115">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="70cfc-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="70cfc-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="70cfc-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70cfc-117">Valor booleano que especifica si cada mensaje contiene una marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="70cfc-117">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="70cfc-118">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="70cfc-118">KeyEntropyMode</span></span>  

 <span data-ttu-id="70cfc-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="70cfc-119">Data type: string</span></span>  
  
 <span data-ttu-id="70cfc-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="70cfc-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70cfc-121">Origen de la entropía utilizada para crear claves.</span><span class="sxs-lookup"><span data-stu-id="70cfc-121">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="70cfc-122">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="70cfc-122">LocalServiceSecuritySettings</span></span>  

 <span data-ttu-id="70cfc-123">Tipo de datos: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="70cfc-123">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="70cfc-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="70cfc-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70cfc-125">Las propiedades de seguridad específicas del enlace del servicio local.</span><span class="sxs-lookup"><span data-stu-id="70cfc-125">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="70cfc-126">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="70cfc-126">MessageSecurityVersion</span></span>  

 <span data-ttu-id="70cfc-127">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="70cfc-127">Data type: string</span></span>  
  
 <span data-ttu-id="70cfc-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="70cfc-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70cfc-129">Versión utilizada para la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="70cfc-129">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="70cfc-130">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="70cfc-130">SecurityHeaderLayout</span></span>  

 <span data-ttu-id="70cfc-131">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="70cfc-131">Data type: string</span></span>  
  
 <span data-ttu-id="70cfc-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="70cfc-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70cfc-133">Orden de los elementos en el encabezado de seguridad de este enlace.</span><span class="sxs-lookup"><span data-stu-id="70cfc-133">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70cfc-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70cfc-134">Requirements</span></span>  
  
|<span data-ttu-id="70cfc-135">MOF</span><span class="sxs-lookup"><span data-stu-id="70cfc-135">MOF</span></span>|<span data-ttu-id="70cfc-136">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="70cfc-136">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="70cfc-137">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="70cfc-137">Namespace</span></span>|<span data-ttu-id="70cfc-138">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="70cfc-138">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70cfc-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="70cfc-139">See also</span></span>

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
