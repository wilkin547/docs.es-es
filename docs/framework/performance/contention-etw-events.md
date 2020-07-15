---
title: 'Eventos ETW de contención: .NET'
description: Obtenga detalles sobre los eventos ETW de contención, que se generan cada vez que hay contención para los bloqueos System. Threading. monitor o bloqueos nativos utilizados por el motor en tiempo de ejecución.
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: a36b091e0896562fffdb66e895d70049ce0667d7
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309604"
---
# <a name="contention-etw-events"></a>Eventos ETW de contención

Los eventos de contención se generan cuando el tiempo de ejecución usa contención de bloqueos <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativos. La contención se produce cuando un subproceso espera un bloqueo mientras otro posee el bloqueo.

En la tabla siguiente se muestra la palabra clave bajo la que se generan los eventos de contención y el nivel de los eventos. Para obtener más información, vea [palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md).

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Informativo (4)|

En la tabla siguiente se muestra la información del evento:

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|81|Se inicia la contención. Este evento no incluye la cantidad de tiempo de giro antes de que un subproceso comience a esperar para adquirir un bloqueo; solo se genera cuando el subproceso espera para adquirir un bloqueo.|
|`ContentionStop`|91|Finaliza la contención.|

En la tabla siguiente se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|Marcas|win:UInt8|0 para administrado; 1 para nativo.|
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR.|

## <a name="see-also"></a>Consulte también

- [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)
