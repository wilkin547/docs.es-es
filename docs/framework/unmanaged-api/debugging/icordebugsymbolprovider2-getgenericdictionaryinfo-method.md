---
title: ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)
ms.date: 03/30/2017
ms.assetid: ba28fe4e-5491-4670-bff7-7fde572d7593
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34ed39d5fe9b820020d777fb3b33c950717059e9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645545"
---
# <a name="icordebugsymbolprovider2getgenericdictionaryinfo-method"></a>ICorDebugSymbolProvider2::GetGenericDictionaryInfo (método)
Recupera una asignación de diccionario genérico.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetGenericDictionaryInfo(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppMemoryBuffer`  
 [out] Un puntero a la dirección de un [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) objeto que contiene la asignación de diccionario genérico. Vea la sección Comentarios para obtener más información.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
 La asignación se compone de dos secciones de nivel superior:  
  
- Un [directory](#Directory) que contiene las direcciones virtuales relativas (RVA) de todos los diccionarios incluidos en esta asignación.  
  
- Una alineación de bytes [montón](#Heap) que contiene información de la creación de instancias de objeto. Se inicia inmediatamente después de la última entrada de directorio.  
  
<a name="Directory"></a>   
## <a name="the-directory"></a>El directorio  
 Cada entrada del directorio hace referencia a un desplazamiento dentro del montón; es decir, es un desplazamiento relativo al inicio del montón. El valor de las entradas individuales no es necesariamente único; varias entradas de directorio pueden apuntar al mismo desplazamiento en el montón.  
  
 La parte del directorio de la asignación del diccionario genérico tiene la estructura siguiente:  
  
- Los primeros cuatro bytes contienen el número de entradas del diccionario (es decir, el número de direcciones virtuales relativas en el diccionario). Nos referiremos a este valor como *N*. Si se establece el bit alto, las entradas se ordenan por la dirección virtual relativa en orden ascendente.  
  
- El *N* siguen las entradas de directorio. Cada entrada consta de 8 bytes, en dos segmentos de 4 bytes:  
  
    - Bytes 0-3: RVA; dirección virtual relativa del diccionario.  
  
    - Bytes 4-7: Desplazamiento; un desplazamiento relativo al inicio del montón.  
  
<a name="Heap"></a>   
## <a name="the-heap"></a>El montón  
 El tamaño del montón se puede calcular con un lector de secuencias restando la longitud de la secuencia del tamaño del directorio + 4. En otras palabras:  
  
```  
Heap Size = Stream.Length – (Directory Size + 4)  
```  
  
 donde el tamaño del directorio es `N * 8`.  
  
 El formato de cada elemento de información sobre la creación de instancias en el montón es:  
  
- La longitud de este elemento de información sobre la creación de instancias en bytes, en el formato de metadatos ECMA comprimido. El valor excluye esta información de longitud.  
  
- El número de tipos de creación de instancias genérica, o *T*, en formato de metadatos ECMA comprimido.  
  
- *T* tipos, cada uno representado en el formato de firma del tipo ECMA.  
  
 Incluir la longitud de cada elemento del montón permite la ordenación simple de la sección del directorio sin afectar al montón.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugSymbolProvider2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
