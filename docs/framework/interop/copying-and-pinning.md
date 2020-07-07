---
title: Copiar y fijar
description: Revise cómo el serializador de interoperabilidad puede copiar o anclar los datos que se están serializando. Copie los datos y coloque una copia de una ubicación de memoria en otra.
ms.date: 03/30/2017
helpviewer_keywords:
- pinning, interop marshaling
- copying, interop marshaling
- interop marshaling, copying
- interop marshaling, pinning
ms.assetid: 0059f576-e460-4e70-b257-668870e420b8
ms.openlocfilehash: b7931813cd5254375eda81515f388c85c78fa284
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618784"
---
# <a name="copying-and-pinning"></a>Copiar y fijar

Al serializar datos, el serializador de interoperabilidad puede copiar o anclar los datos que se van a serializar. Copiar los datos coloca una copia de datos desde una ubicación de memoria en otra. En la siguiente ilustración se muestran las diferencias entre copiar un tipo de valor y copiar un tipo pasado por referencia de memoria administrada a memoria no administrada.

![Diagrama que muestra cómo se copian los tipos de referencia y valor.](./media/copying-and-pinning/interop-marshal-copy.gif)

Los argumentos de método pasados por valor se serializan en código no administrado como valores de la pila. El proceso de copia es directo. Los argumentos que se pasan por referencia se pasan como punteros en la pila. Los tipos de referencia también se pasan por valor y por referencia. Como se muestra en la siguiente ilustración, los tipos de referencia pasados por valor se copian o se anclan:

![Diagrama que muestra los tipos de referencia pasados por valor y por referencia.](./media/copying-and-pinning/interop-marshal-reference-pin.gif)

Anclar bloquea temporalmente los datos en su ubicación de memoria actual, lo que evita que el recolector de elementos no utilizados de Common Language Runtime los reubique. El serializador ancla los datos para reducir la sobrecarga de la copia y mejorar el rendimiento. El tipo de los datos determina si se copian o se anclan durante el proceso de serialización.  El anclaje se realiza automáticamente durante la serialización para objetos como <xref:System.String>, pero también se puede anclar manualmente la memoria mediante la clase <xref:System.Runtime.InteropServices.GCHandle>.

## <a name="formatted-blittable-classes"></a>Clases que pueden transferirse en bloque de bits con formato

Las clases [que pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md) con formato tienen una distribución (con formato) y representación común de datos fijas tanto en la memoria administrada como no administrada. Cuando estos tipos requieren serialización, se pasa directamente un puntero al objeto en el montón al destinatario de la llamada. El destinatario de la llamada puede cambiar el contenido de la ubicación de memoria a la que hace referencia el puntero.

> [!NOTE]
> El destinatario puede cambiar el contenido de la memoria si el parámetro está marcado como Out o In/Out. En cambio, el destinatario debe evitar cambiar el contenido cuando el parámetro se establece para serializarse como In, que es el valor predeterminado para tipos que pueden transferirse en bloque de bits. Modificar un objeto In genera problemas cuando se exporta la misma clase a una biblioteca de tipos y se usa para realizar llamadas entre contenedores.

## <a name="formatted-non-blittable-classes"></a>Clases que no pueden transferirse en bloque de bits con formato

Las clases [que no pueden transferirse en bloque de bits](blittable-and-non-blittable-types.md) con formato tienen una distribución fija (con formato) pero la representación de datos es diferente en la memoria administrada y la no administrada. Los datos pueden requerir transformación en las siguientes condiciones:

- Si una clase que no puede transferirse en bloque de bits se serializa por valor, el destinatario de la llamada recibe un puntero a una copia de la estructura de datos.

- Si una clase que no puede transferirse en bloque de bits se serializa por referencia, el destinatario de la llamada recibe un puntero a un puntero a una copia de la estructura de datos.

- Si se establece el atributo <xref:System.Runtime.InteropServices.InAttribute>, esta copia siempre se inicializa con el estado de la instancia, y se serializa según sea necesario.

- Si se establece el atributo <xref:System.Runtime.InteropServices.OutAttribute>, el estado siempre se copia de vuelta en la instancia, y se serializa según sea necesario.

- Si se establecen **InAttribute** y **OutAttribute**, se requieren ambas copias. Si se omite uno de los atributos, el serializador puede optimizar mediante la eliminación de cualquiera de las copias.

## <a name="reference-types"></a>Tipos de referencia

Los tipos de referencia se pueden pasar por valor o por referencia. Cuando se pasan por valor, se pasa un puntero al tipo en la pila. Cuando se pasan por referencia, se pasa un puntero a un puntero al tipo en la pila.

Los tipos de referencia tienen el siguiente comportamiento condicional:

- Si un tipo de referencia se pasa por valor y tiene miembros de tipos que no pueden transferirse en bloque de bits, los tipos se convierten dos veces:

  - Cuando se pasa un argumento al lado no administrado.

  - En la devolución de la llamada.

  Para evitar copias y conversiones innecesarias, estos tipos se serializan como parámetros In. Debe aplicar explícitamente los atributos **InAttribute** y **OutAttribute** a un argumento para que el autor de la llamada vea los cambios realizados por el destinatario.

- Si un tipo de referencia se pasa por valor y solo tiene miembros de tipos que pueden transferirse en bloque de bits, se puede anclar durante la serialización y el autor de la llamada verá cualquier cambio realizado en los miembros del tipo por el destinatario. Aplique **InAttribute** y **OutAttribute** explícitamente si quiere este comportamiento. Sin estos atributos direccionales, el serializador de interoperabilidad no exporta información direccional a la biblioteca de tipos (se exporta como In, que es el valor predeterminado) y esto puede causar problemas con la serialización COM entre contenedores.

- Si un tipo de referencia se pasa por referencia, se serializará como In/Out de forma predeterminada.

## <a name="systemstring-and-systemtextstringbuilder"></a>System.String y System.Text.StringBuilder

Cuando los datos se serializan en código no administrado por valor o por referencia, el serializador normalmente copia los datos en un búfer secundario (y posiblemente convierte los juegos de caracteres durante la copia) y pasa una referencia al búfer al destinatario de la llamada. A menos que la referencia sea un **BSTR** asignado con **SysAllocString**, la referencia siempre se asigna con **CoTaskMemAlloc**.

Como una optimización cuando se serializa por valor cualquier tipo de cadena (por ejemplo, una cadena de caracteres Unicode), el serializador pasa al destinatario de la llamada un puntero directo a las cadenas administradas en el búfer interno de Unicode en lugar de copiarlo en un búfer nuevo.

> [!CAUTION]
> Cuando se pasa una cadena por valor, el destinatario nunca debe modificar la referencia que pasa el serializador. Esto puede dañar el montón administrado.

Cuando se pasa <xref:System.String?displayProperty=nameWithType> por referencia, el serializador copia el contenido de la cadena en un búfer secundario antes de realizar la llamada. Después, copia el contenido del búfer en una nueva cadena en la devolución de la llamada. Esta técnica garantiza que la cadena administrada inmutable permanece sin modificar.

Cuando se pasa <xref:System.Text.StringBuilder?displayProperty=nameWithType> por valor, el serializador pasa una referencia al búfer interno de **StringBuilder** directamente al autor de la llamada. El autor de la llamada y el destinatario deben acordar el tamaño del búfer. El autor de la llamada es responsable de crear un **StringBuilder** de la longitud adecuada. El destinatario debe tomar las precauciones necesarias para asegurarse de que el búfer no se desborda. **StringBuilder** es una excepción a la regla de que los tipos de referencia que se pasan por valor se pasan como parámetros In de forma predeterminada. Siempre se pasa como In/Out.

## <a name="see-also"></a>Vea también

- [Comportamiento predeterminado del cálculo de referencias](default-marshaling-behavior.md)
- [Atributos direccionales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [Serialización de interoperabilidad](interop-marshaling.md)
