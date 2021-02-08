---
description: 'Más información sobre: recursos del sistema operativo necesarios para WCF'
title: Recursos del sistema operativo necesarios para WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 717ab2074c0dcf840919c2bd8afa2641e106ac11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779223"
---
# <a name="operating-system-resources-required-by-wcf"></a>Recursos del sistema operativo necesarios para WCF

Windows Communication Foundation (WCF) depende de varios recursos proporcionados por el sistema operativo para que funcionen. En la tabla siguiente se enumeran esos recursos:

|Resource|Descripción|
|--------------|-----------------|
|Microsoft DTC (Coordinador de transacciones distribuidas) |Requerido para admitir las transacciones de OleTx.|
|Servicios de Internet Information Server (IIS)|Requerido si quiere usar IIS para hospedar su aplicación.|
|Servicio de activación de procesos de Windows (WAS)|Requerido si desea utilizar WAS para hospedar su aplicación.|
