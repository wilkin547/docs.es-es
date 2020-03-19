---
title: 'Algoritmo de carga de biblioteca no administrada: .NET Core'
description: Descripción de los detalles del algoritmo de carga de ensamblado no administrado en .NET Core
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72303699"
---
# <a name="unmanaged-native-library-loading-algorithm"></a>Algoritmo de carga de biblioteca no administrada (nativa)

Las bibliotecas no administradas se ubican y se cargan con un algoritmo que implica varias fases.

El algoritmo siguiente describe cómo se cargan las bibliotecas nativas a través de `PInvoke`.

## <a name="pinvoke-load-library-algorithm"></a>Algoritmo de la biblioteca de carga `PInvoke`

`PInvoke` usa el algoritmo siguiente al intentar cargar un ensamblado no administrado:

1. Determine el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active`. En el caso de una biblioteca de carga no administrada, el elemento AssemblyLoadContext de `active` es el que tiene el ensamblado que define `PInvoke`.

2. En el caso del elemento <xref:System.Runtime.Loader.AssemblyLoadContext> `active`, intente buscar el ensamblado en orden de prioridad por:
    * Comprobar la memoria caché.

    * Llamar al delegado <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> actual que establece la función <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType>.

    * Llamar a la función <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> en el elemento AssemblyLoadContext de `active`.

    * Comprobar la memoria caché de la instancia de <xref:System.AppDomain> y ejecutar la lógica de [sondeo de biblioteca no administrada (nativa)](default-probing.md#unmanaged-native-library-probing).

    * Generar el evento <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> para el elemento AssemblyLoadContext de `active`.
