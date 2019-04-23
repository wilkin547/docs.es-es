---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 1d367d0c5d14e6e75539dd2b20cdffcf2b34963d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975564"
---
# <a name="securitybindingelement"></a><span data-ttu-id="ad1d0-102">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ad1d0-102">SecurityBindingElement</span></span>
<span data-ttu-id="ad1d0-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ad1d0-103">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad1d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad1d0-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="ad1d0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ad1d0-105">Methods</span></span>  
 <span data-ttu-id="ad1d0-106">La clase SecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ad1d0-106">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ad1d0-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ad1d0-107">Properties</span></span>  
 <span data-ttu-id="ad1d0-108">La clase SecurityBindingElement posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="ad1d0-108">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="ad1d0-109">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="ad1d0-109">DefaultAlgorithmSuite</span></span>  
 <span data-ttu-id="ad1d0-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ad1d0-110">Data type: string</span></span>  
  
 <span data-ttu-id="ad1d0-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ad1d0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad1d0-112">Especifica los algoritmos que se van a utilizar con la clase.</span><span class="sxs-lookup"><span data-stu-id="ad1d0-112">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="ad1d0-113">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="ad1d0-113">IncludeTimestamp</span></span>  
 <span data-ttu-id="ad1d0-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="ad1d0-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="ad1d0-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ad1d0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad1d0-116">Valor booleano que especifica si cada mensaje contiene una marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ad1d0-116">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="ad1d0-117">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="ad1d0-117">KeyEntropyMode</span></span>  
 <span data-ttu-id="ad1d0-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ad1d0-118">Data type: string</span></span>  
  
 <span data-ttu-id="ad1d0-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ad1d0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad1d0-120">Origen de la entropía utilizada para crear claves.</span><span class="sxs-lookup"><span data-stu-id="ad1d0-120">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="ad1d0-121">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ad1d0-121">LocalServiceSecuritySettings</span></span>  
 <span data-ttu-id="ad1d0-122">Tipo de datos: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="ad1d0-122">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="ad1d0-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ad1d0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad1d0-124">Las propiedades de seguridad específicas del enlace del servicio local.</span><span class="sxs-lookup"><span data-stu-id="ad1d0-124">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="ad1d0-125">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="ad1d0-125">MessageSecurityVersion</span></span>  
 <span data-ttu-id="ad1d0-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ad1d0-126">Data type: string</span></span>  
  
 <span data-ttu-id="ad1d0-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ad1d0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad1d0-128">Versión utilizada para la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ad1d0-128">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="ad1d0-129">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="ad1d0-129">SecurityHeaderLayout</span></span>  
 <span data-ttu-id="ad1d0-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="ad1d0-130">Data type: string</span></span>  
  
 <span data-ttu-id="ad1d0-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="ad1d0-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad1d0-132">Orden de los elementos en el encabezado de seguridad de este enlace.</span><span class="sxs-lookup"><span data-stu-id="ad1d0-132">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad1d0-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad1d0-133">Requirements</span></span>  
  
|<span data-ttu-id="ad1d0-134">MOF</span><span class="sxs-lookup"><span data-stu-id="ad1d0-134">MOF</span></span>|<span data-ttu-id="ad1d0-135">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ad1d0-135">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad1d0-136">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ad1d0-136">Namespace</span></span>|<span data-ttu-id="ad1d0-137">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ad1d0-137">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad1d0-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad1d0-138">See also</span></span>

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
