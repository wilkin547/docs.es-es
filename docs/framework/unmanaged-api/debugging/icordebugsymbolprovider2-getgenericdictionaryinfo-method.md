---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
ms.openlocfilehash: a6c32b72c5924399aeb13d56ddf9242fe7990f35
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379320"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a>ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)

Recupera una asignación de diccionario genérico.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetGenericDictionaryInfo(
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer
);
```

## <a name="parameters"></a>Parámetros

`ppMemoryBuffer`\
enuncia Un puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene la asignación de diccionario genérico. Para obtener más información, vea la sección Comentarios.

## <a name="remarks"></a>Observaciones

> [!NOTE]
> Este método solo está disponible con .NET Native.

La asignación se compone de dos secciones de nivel superior:

- Un [directorio](#Directory) que contiene las direcciones virtuales relativas (RVA) de todos los diccionarios incluidos en esta asignación.

- [Montón](#Heap) alineado en bytes que contiene información sobre la creación de instancias de objetos. Se inicia inmediatamente después de la última entrada de directorio.

<a name="Directory"></a>

## <a name="the-directory"></a>El directorio

Cada entrada del directorio hace referencia a un desplazamiento dentro del montón; es decir, es un desplazamiento relativo al inicio del montón. El valor de las entradas individuales no es necesariamente único; varias entradas de directorio pueden apuntar al mismo desplazamiento en el montón.

La parte del directorio de la asignación del diccionario genérico tiene la estructura siguiente:

- Los primeros cuatro bytes contienen el número de entradas del diccionario (es decir, el número de direcciones virtuales relativas en el diccionario). Haremos referencia a este valor como *N*. Si se establece el bit alto, las entradas se ordenan por dirección virtual relativa en orden ascendente.

- Las *N* entradas de directorio siguen. Cada entrada consta de 8 bytes, en dos segmentos de 4 bytes:

  - Bytes de 0 a 3: RVA; dirección virtual relativa del diccionario.

  - Bytes de 4 a 7: desplazamiento; un desplazamiento relativo al inicio del montón.

<a name="Heap"></a>

## <a name="the-heap"></a>El montón

El tamaño del montón se puede calcular con un lector de secuencias restando la longitud de la secuencia del tamaño del directorio + 4. En otras palabras:

```csharp
Heap Size = Stream.Length – (Directory Size + 4)
```

donde el tamaño del directorio es `N * 8`.

El formato de cada elemento de información sobre la creación de instancias en el montón es:

- La longitud de este elemento de información sobre la creación de instancias en bytes, en el formato de metadatos ECMA comprimido. El valor excluye esta información de longitud.

- El número de tipos de creación de instancias genéricos, o *T*, en formato de metadatos ECMA comprimido.

- Tipos *T* , cada uno representado en el formato de firma de tipo ECMA.

Incluir la longitud de cada elemento del montón permite la ordenación simple de la sección del directorio sin afectar al montón.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]

## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
