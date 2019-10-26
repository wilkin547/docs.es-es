---
title: Recursos del sistema operativo necesarios para WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961135"
---
# <a name="operating-system-resources-required-by-wcf"></a>Recursos del sistema operativo necesarios para WCF

Windows Communication Foundation (WCF) depende de varios recursos proporcionados por el sistema operativo para que funcionen. En la tabla siguiente se enumeran esos recursos:

|Recurso|Descripción|
|--------------|-----------------|
|Microsoft DTC (Coordinador de transacciones distribuidas)|Requerido para admitir las transacciones de OleTx.|
|Internet Information Services (IIS)|Requerido si quiere usar IIS para hospedar su aplicación.|
|Servicio de activación de procesos de Windows (WAS)|Requerido si desea utilizar WAS para hospedar su aplicación.|
