---
description: 'Más información acerca de: 1004-WorkflowInstanceAborted'
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: 4aaa0899da9b0b8510684a13537a8cb8f9117ee1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755627"
---
# <a name="1004---workflowinstanceaborted"></a>1004 - WorkflowInstanceAborted

## <a name="properties"></a>Propiedades

|||
|-|-|
|Id.|1004|
|Palabras clave|WFRuntime|
|Nivel|Información|
|Canal|Microsoft-Windows-Application Server-Applications/Debug|

## <a name="description"></a>Descripción

Indica que una instancia de flujo de trabajo se ha anulado con una excepción.

## <a name="message"></a>Message

WorkflowInstance Id: '%1' se anuló con una excepción.

## <a name="details"></a>Detalles

|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|
|--------------------|--------------------|-----------------|
|WorkflowInstanceId|`xs:string`|El id. de instancia del flujo de trabajo.|
|Excepción|`xs:string`|Detalles de la excepción para la excepción|
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
