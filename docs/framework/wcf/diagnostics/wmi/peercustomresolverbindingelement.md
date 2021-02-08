---
description: 'Más información acerca de: PeerCustomResolverBindingElement'
title: PeerCustomResolverBindingElement
ms.date: 03/30/2017
ms.assetid: 9ccc2770-a20e-4dff-9970-f56ad8aec2b5
ms.openlocfilehash: f4277c04818eec69c1041eee30282d3111421eaa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803053"
---
# <a name="peercustomresolverbindingelement"></a>PeerCustomResolverBindingElement

PeerCustomResolverBindingElement

## <a name="syntax"></a>Sintaxis

```csharp
class PeerCustomResolverBindingElement : PeerResolverBindingElement
{
    string Address;
    string Binding;
};
```

## <a name="methods"></a>Métodos

La clase PeerCustomResolverBindingElement no define ningún método.

## <a name="properties"></a>Propiedades

 La clase PeerCustomResolverBindingElement tiene las propiedades siguientes:

### <a name="address"></a>Dirección

Tipo de datos: cadena

Tipo de acceso: solo lectura

La dirección de la resolución personalizada del mismo nivel.

### <a name="binding"></a>Enlace

Tipo de datos: cadena

Tipo de acceso: solo lectura

Nombre de configuración del enlace.

## <a name="requirements"></a>Requisitos

|MOF|Se declara en Servicemodel.mof.|
|---------|-----------------------------------|
|Espacio de nombres|Se define en root\ServiceModel|

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement>
