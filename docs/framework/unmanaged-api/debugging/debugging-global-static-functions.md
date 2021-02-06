---
description: 'Más información sobre: depurar funciones estáticas globales'
title: Funciones estáticas globales para la depuración
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
ms.openlocfilehash: efee1bfb6eb61ae2311320a4c12bf08ec0f9534b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661459"
---
# <a name="debugging-global-static-functions"></a>Funciones estáticas globales para la depuración

Esta sección describe las funciones estáticas globales no administradas que utiliza la API de depuración.  
  
## <a name="in-this-section"></a>En esta sección  

 [_EFN_GetManagedExcepStack (Función)](efn-getmanagedexcepstack-function.md)  
 Dada una dirección de objeto de excepción administrado, devuelve una versión de cadena del seguimiento de pila que contiene.  
  
 [_EFN_GetManagedObjectFieldInfo (Función)](efn-getmanagedobjectfieldinfo-function.md)  
 Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.  
  
 [_EFN_GetManagedObjectName (Función)](efn-getmanagedobjectname-function.md)  
 Obtiene el nombre de un tipo mediante el puntero de objeto administrado proporcionado.  
  
 [_EFN_StackTrace (Función)](efn-stacktrace-function.md)  
 Proporciona una representación de texto de un seguimiento de pila administrado y una matriz de registros `CONTEXT`, uno por cada transición entre código no administrado y código administrado.  
  
 [CLRDataCreateInstance (Función)](clrdatacreateinstance-function.md)  
 Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para crear el objeto de interfaz especificado para el proceso de destino especificado.  
  
 [puntero a la función PFN_CLRDataCreateInstance](pfn-clrdatacreateinstance-function-pointer.md)  
 Señala una función a la que llaman los servicios de acceso a datos de CLR para crear el objeto de interfaz especificado para el proceso de destino especificado.  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Coclases para la depuración](debugging-coclasses.md)  
  
 [Interfaces para depuración](debugging-interfaces.md)  
  
 [Enumeraciones de depuración](debugging-enumerations.md)  
  
 [Estructuras de depuración](debugging-structures.md)
