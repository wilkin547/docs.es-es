---
title: Ejemplos de REF CURSOR
ms.date: 03/30/2017
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
ms.openlocfilehash: dc82648ff5a565c9b4d6fa593433ee1e22249d93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149140"
---
# <a name="ref-cursor-examples"></a>Ejemplos de REF CURSOR
Los ejemplos de cursores REF CURSOR constan de los siguientes tres ejemplos de Microsoft Visual Basic que muestran el uso de los cursores REF CURSOR.  
  
|Muestra|Descripción|  
|------------|-----------------|  
|[Parámetros REF CURSOR en un objeto OracleDataReader](ref-cursor-parameters-in-an-oracledatareader.md)|En este ejemplo se ejecuta un procedimiento almacenado PL/SQL que devuelve un parámetro REF CURSOR y lee el valor como un <xref:System.Data.OracleClient.OracleDataReader>.|  
|[Recuperar datos desde varios parámetros REF CURSOR utilizando un objeto OracleDataReader](retrieving-data-from-multiple-ref-cursors.md)|En este ejemplo se ejecuta un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y lee los valores mediante **OracleDataReader**.|  
|[Rellenar un conjunto de datos utilizando uno o varios parámetros REF CURSOR](filling-a-dataset-using-one-or-more-ref-cursors.md)|En este ejemplo se ejecuta un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y llena un <xref:System.Data.DataSet> con las filas que se devuelven.|  
  
 Para utilizar estos ejemplos, puede que tenga que crear las tablas de Oracle, y deberá crear un paquete PL/SQL y el cuerpo del paquete.  
  
## <a name="creating-the-oracle-tables"></a>Creación de las tablas de Oracle  
 En estos ejemplos se utilizan tablas que se definen en el esquema Scott/Tiger de Oracle. El esquema Scott/Tiger de Oracle se incluye en la mayoría de las instalaciones de Oracle. Si no existe este esquema, puede utilizar el archivo de comandos SQL situado en {OracleHome}\rdbms\admin\scott.sql para crear las tablas y los índices necesarios para estos ejemplos.  
  
## <a name="creating-the-oracle-package-and-package-body"></a>Creación del paquete de Oracle y el cuerpo del paquete  
 En estos ejemplos es necesario el siguiente paquete PL/SQL y cuerpo del paquete en el servidor. Cree el siguiente paquete de Oracle en el servidor de Oracle.  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS
    TYPE T_CURSOR IS REF CURSOR;
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,
                               IO_CURSOR IN OUT T_CURSOR);
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/
```  
  
 Cree el siguiente cuerpo del paquete de Oracle en el servidor Oracle.  
  
```sql
CREATE OR REPLACE PACKAGE BODY CURSPKG AS  
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,  
                               IO_CURSOR IN OUT T_CURSOR)  
    IS
        V_CURSOR T_CURSOR;
    BEGIN
        IF N_EMPNO <> 0
        THEN  
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO
                  AND EMP.EMPNO = N_EMPNO;  
  
        ELSE
             OPEN V_CURSOR FOR
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME
                  FROM EMP, DEPT
                  WHERE EMP.DEPTNO = DEPT.DEPTNO;  
  
        END IF;  
        IO_CURSOR := V_CURSOR;
    END OPEN_ONE_CURSOR;
  
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,  
                                DEPTCURSOR OUT T_CURSOR)  
    IS
        V_CURSOR1 T_CURSOR;
        V_CURSOR2 T_CURSOR;
    BEGIN
        OPEN V_CURSOR1 FOR SELECT * FROM EMP;  
        OPEN V_CURSOR2 FOR SELECT * FROM DEPT;  
        EMPCURSOR  := V_CURSOR1;
        DEPTCURSOR := V_CURSOR2;
    END OPEN_TWO_CURSORS;
END CURSPKG;  
/  
```  
  
## <a name="see-also"></a>Consulte también

- [Parámetros REF CURSOR de Oracle](oracle-ref-cursors.md)
- [Información general de ADO.NET](ado-net-overview.md)
