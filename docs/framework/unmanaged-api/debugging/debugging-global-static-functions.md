---
title: Funciones estáticas globales para la depuración
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2403d736d031aab52525fc12b5071e764a8bde1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-global-static-functions"></a>Funciones estáticas globales para la depuración
Esta sección describe las funciones estáticas globales no administradas que utiliza la API de depuración.  
  
## <a name="in-this-section"></a>En esta sección  
 [_EFN_GetManagedExcepStack (función)](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedexcepstack-function.md)  
 Dada una dirección de objeto de excepción administrado, devuelve una versión de cadena del seguimiento de pila que contiene.  
  
 [_EFN_GetManagedObjectFieldInfo (Función)](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectfieldinfo-function.md)  
 Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.  
  
 [_EFN_GetManagedObjectName (Función)](../../../../docs/framework/unmanaged-api/debugging/efn-getmanagedobjectname-function.md)  
 Obtiene el nombre de un tipo mediante el puntero de objeto administrado proporcionado.  
  
 [_EFN_StackTrace (Función)](../../../../docs/framework/unmanaged-api/debugging/efn-stacktrace-function.md)  
 Proporciona una representación de texto de un seguimiento de pila administrado y una matriz de registros `CONTEXT`, uno por cada transición entre código no administrado y código administrado.  
  
 [CLRDataCreateInstance (Función)](../../../../docs/framework/unmanaged-api/debugging/clrdatacreateinstance-function.md)  
 Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para crear el objeto de interfaz especificado para el proceso de destino especificado.  
  
 [PFN_CLRDataCreateInstance (puntero de función)](../../../../docs/framework/unmanaged-api/debugging/pfn-clrdatacreateinstance-function-pointer.md)  
 Señala una función a la que llaman los servicios de acceso a datos de CLR para crear el objeto de interfaz especificado para el proceso de destino especificado.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
