---
title: 'Mitigación: Nuevo compilador JIT de 64 bits'
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compiler, 64-bit
- JIT compilation, 64-bit
- RyuJIT compiler
ms.assetid: 0332dabc-72c5-4bdc-8975-20d717802b17
ms.openlocfilehash: 883aaf032bde632b08f965d3450cfbea4feb8e65
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181253"
---
# <a name="mitigation-new-64-bit-jit-compiler"></a>Mitigación: Nuevo compilador JIT de 64 bits
A partir de .NET Framework 4.6, el tiempo d ejecución incluye un nuevo compilador JIT de 64 bits para la compilación Just-In-Time. Este cambio no afecta a la compilación con el compilador JIT de 32 bits.  
  
## <a name="unexpected-behavior-or-exceptions"></a>Comportamiento inesperado o excepciones  
 En algunos casos, la compilación con el nuevo compilador JIT de 64 bits provoca una excepción en tiempo de ejecución o en el comportamiento que no se observa al ejecutar el código compilado por el compilador JIT de 64 bits antiguo. Las diferencias conocidas incluyen lo siguiente:  
  
> [!IMPORTANT]
> Todos estos problemas conocidos se han solucionado en el nuevo compilador de 64 bits publicado con .NET Framework 4.6.2. También se han abordado la mayoría en las versiones de servicio de .NET Framework 4.6 y 4.6.1 que se incluyen con Windows Update. Puede eliminar estos problemas asegurándose de que la versión de Windows está actualizada o actualizando a .NET Framework 4.6.2.  
  
- En determinadas condiciones, una operación de conversión unboxing puede producir una <xref:System.NullReferenceException> en versiones de lanzamiento con la optimización activada.  
  
- En algunos casos, la ejecución del código de producción en un cuerpo del método de gran tamaño puede producir una <xref:System.StackOverflowException>.  
  
- En determinadas condiciones, las estructuras que pasan a un método se tratan como tipos de referencia en lugar de tipos de valor en las compilaciones de versión. Una de las manifestaciones de este problema es que los elementos individuales de una colección aparecen en un orden inesperado.  
  
- En determinadas condiciones, la comparación de los valores <xref:System.UInt16> con su conjunto de bits altos es incorrecta si se habilita la optimización.  
  
- En determinadas condiciones, especialmente al indexar los valores de matriz, la inicialización de la memoria mediante la instrucción IL <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> puede inicializar la memoria con un valor incorrecto. Esto puede producir una excepción no controlada o resultados incorrectos.  
  
- En determinadas condiciones poco frecuentes, una prueba de bits condicional puede devolver el valor <xref:System.Boolean> incorrecto o producir una excepción si se habilitan las optimizaciones del compilador.  
  
- En determinadas condiciones, si se utiliza una instrucción `if` para comprobar una condición antes de entrar en un bloque `try` y en la salida del bloque `try`, y se evalúa la misma condición en el bloque `catch` o `finally`, el compilador JIT de 64 bits nuevo quita la condición `if` del bloque `catch` o `finally` cuando optimiza el código. Como resultado, el código dentro de la instrucción `if` en el bloque `catch` o `finally` se ejecuta de forma incondicional.  
  
<a name="General"></a>
## <a name="mitigation-of-known-issues"></a>Mitigación de problemas conocidos  
 Si encuentra los problemas mencionados anteriormente, puede solucionarlos realizando las siguientes operaciones:  
  
- Actualizar a the .NET Framework 4.6.2. El nuevo compilador de 64 bits incluido con .NET Framework 4.6.2 soluciona estos problemas conocidos.  
  
- Asegurarse de que su versión Windows está actualizada ejecutando Windows Update. Las actualizaciones de servicio de .NET Framework 4.6 y 4.6.1 solucionan los problemas excepto <xref:System.NullReferenceException> en una operación de conversión unboxing.  
  
- Compilación con el compilador JIT de 64 bits más antiguo. Vea la sección [Mitigación de otros problemas](#Other) sección para obtener más información sobre el procedimiento.  
  
<a name="Other"></a>
## <a name="mitigation-of-other-issues"></a>Mitigación de otros problemas  
 Si detecta cualquier otra diferencia en el comportamiento entre el código compilado con el compilador de 64 bits antiguo y el compilador de 64 bits nuevo, o entre las versiones de depuración y publicación de la aplicación que se compilan con el nuevo compilador JIT de 64 bits, puede realizar el siguiente procedimiento para compilar la aplicación con el compilador JIT de 64 bits anterior:  
  
- Según la aplicación, se puede agregar el elemento [\<useLegacyJit>](../configure-apps/file-schema/runtime/uselegacyjit-element.md) al archivo de configuración de la aplicación. Lo siguiente deshabilita la compilación con el nuevo compilador JIT de 64 bits y en su lugar usa el compilador JIT de 64 bits hereado.  
  
    ```xml  
    <?xml version ="1.0"?>  
    <configuration>  
        <runtime>  
           <useLegacyJit enabled="1" />  
        </runtime>  
    </configuration>  
    ```  
  
- Según el usuario, puede agregar un valor `REG_DWORD` con el nombre `useLegacyJit` a la clave `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` del registro. El valor 1 permite al compilador JIT de 64 bits hereado; un valor de 0 lo deshabilita y habilita el nuevo compilador JIT de 64 bits.  
  
- Según el equipo, puede agregar un valor `REG_DWORD` con el nombre `useLegacyJit` a la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` del registro. El valor 1 permite al compilador JIT de 64 bits hereado; un valor de 0 lo deshabilita y habilita el nuevo compilador JIT de 64 bits.  
  
 También puede informar del problema indicándonos el error en [Microsoft Connect](https://connect.microsoft.com/VisualStudio).  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
- [Elemento \<useLegacyJIT>](../configure-apps/file-schema/runtime/uselegacyjit-element.md)
