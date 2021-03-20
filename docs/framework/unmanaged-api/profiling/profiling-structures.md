---
description: 'Más información sobre: estructuras de generación de perfiles'
title: Estructuras para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: 176830cac519f22864ba004b176cb575d80e50e2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760241"
---
# <a name="profiling-structures"></a>Estructuras para generación de perfiles

En esta sección se describen las estructuras no administradas que utiliza la API de generación de perfiles.  
  
## <a name="in-this-section"></a>En esta sección  

 [COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)](cor-prf-assembly-reference-info-structure.md)  
 Proporciona a Common Language Runtime información sobre una referencia de ensamblado que debe tener en cuenta a la hora de realizar un rastreo de cierre de referencias de ensamblado.  
  
 [COR_PRF_CODE_INFO (Estructura)](cor-prf-code-info-structure.md)  
 Representa un bloque contiguo de código nativo almacenado en la memoria.  
  
 [COR_PRF_EX_CLAUSE_INFO (Estructura)](cor-prf-ex-clause-info-structure.md)  
 Almacena información sobre una instancia específica de cláusula de excepción y su marco asociado.  
  
 [COR_PRF_FUNCTION (Estructura)](cor-prf-function-structure.md)  
 Proporciona una representación única de una función combinando su identificador con el identificador de la versión que se ha vuelto a compilar.  
  
 [COR_PRF_FUNCTION_ARGUMENT_INFO (Estructura)](cor-prf-function-argument-info-structure.md)  
 Representa los argumentos de una función, ordenados de izquierda a derecha.  
  
 [COR_PRF_FUNCTION_ARGUMENT_RANGE (Estructura)](cor-prf-function-argument-range-structure.md)  
 Representa un bloque de argumentos de función almacenados en la memoria de forma contigua, ordenados de izquierda a derecha.  
  
 [COR_PRF_GC_GENERATION_RANGE (Estructura)](cor-prf-gc-generation-range-structure.md)  
 Describe un intervalo (es decir, un bloque) de memoria sometida a recopilación de elementos no utilizados.  

 [Estructura de COR_PRF_EVENTPIPE_PROVIDER_CONFIG](cor-prf-eventpipe-provider-config-structure.md) Describe los campos necesarios para configurar un proveedor de EventPipe.

 [Estructura de COR_PRF_EVENTPIPE_PARAM_DESC](cor-prf-eventpipe-param-desc-structure.md) Describe el nombre y el tipo de parámetro de un evento EventPipe.

 [Estructura de COR_PRF_EVENT_DATA](cor-prf-event-data-structure.md) Describe los datos de evento para un evento EventPipe que se está escribiendo.
  
## <a name="related-sections"></a>Secciones relacionadas  

 COR_DEBUG_IL_TO_NATIVE_MAP  
  
 COR_IL_MAP  
  
 [Información general sobre la generación de perfiles](profiling-overview.md)  
  
 [Interfaces para generación de perfiles](profiling-interfaces.md)  
  
 [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)  
  
 [Enumeraciones para generación de perfiles](profiling-enumerations.md)
