---
title: Colecciones de esquemas de ODBC
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b8c31f4e8b1463c184c9a8ff1cf64808783f030d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="309ec-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="309ec-102">ODBC Schema Collections</span></span>
<span data-ttu-id="309ec-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="309ec-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="309ec-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="309ec-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="309ec-105">El controlador ODBC de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="309ec-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="309ec-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="309ec-106">Tables</span></span>  
  
-   <span data-ttu-id="309ec-107">Índices</span><span class="sxs-lookup"><span data-stu-id="309ec-107">Indexes</span></span>  
  
-   <span data-ttu-id="309ec-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="309ec-108">Columns</span></span>  
  
-   <span data-ttu-id="309ec-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="309ec-109">Procedures</span></span>  
  
-   <span data-ttu-id="309ec-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309ec-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="309ec-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309ec-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="309ec-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="309ec-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="309ec-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="309ec-113">Tables and Views</span></span>  
  
|<span data-ttu-id="309ec-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-114">ColumnName</span></span>|<span data-ttu-id="309ec-115">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="309ec-116">TABLE_CAT</span></span>|<span data-ttu-id="309ec-117">String</span><span class="sxs-lookup"><span data-stu-id="309ec-117">String</span></span>|  
|<span data-ttu-id="309ec-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309ec-118">TABLE_SCHEM</span></span>|<span data-ttu-id="309ec-119">String</span><span class="sxs-lookup"><span data-stu-id="309ec-119">String</span></span>|  
|<span data-ttu-id="309ec-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-120">TABLE_NAME</span></span>|<span data-ttu-id="309ec-121">String</span><span class="sxs-lookup"><span data-stu-id="309ec-121">String</span></span>|  
|<span data-ttu-id="309ec-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-122">TABLE_TYPE</span></span>|<span data-ttu-id="309ec-123">String</span><span class="sxs-lookup"><span data-stu-id="309ec-123">String</span></span>|  
|<span data-ttu-id="309ec-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-124">REMARKS</span></span>|<span data-ttu-id="309ec-125">String</span><span class="sxs-lookup"><span data-stu-id="309ec-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="309ec-126">Índices</span><span class="sxs-lookup"><span data-stu-id="309ec-126">Indexes</span></span>  
  
|<span data-ttu-id="309ec-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-127">ColumnName</span></span>|<span data-ttu-id="309ec-128">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="309ec-129">TABLE_CAT</span></span>|<span data-ttu-id="309ec-130">String</span><span class="sxs-lookup"><span data-stu-id="309ec-130">String</span></span>|  
|<span data-ttu-id="309ec-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309ec-131">TABLE_SCHEM</span></span>|<span data-ttu-id="309ec-132">String</span><span class="sxs-lookup"><span data-stu-id="309ec-132">String</span></span>|  
|<span data-ttu-id="309ec-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-133">TABLE_NAME</span></span>|<span data-ttu-id="309ec-134">String</span><span class="sxs-lookup"><span data-stu-id="309ec-134">String</span></span>|  
|<span data-ttu-id="309ec-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="309ec-135">NON_UNIQUE</span></span>|<span data-ttu-id="309ec-136">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-136">Int16</span></span>|  
|<span data-ttu-id="309ec-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="309ec-138">String</span><span class="sxs-lookup"><span data-stu-id="309ec-138">String</span></span>|  
|<span data-ttu-id="309ec-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-139">INDEX_NAME</span></span>|<span data-ttu-id="309ec-140">String</span><span class="sxs-lookup"><span data-stu-id="309ec-140">String</span></span>|  
|<span data-ttu-id="309ec-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-141">TYPE</span></span>|<span data-ttu-id="309ec-142">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-142">Int16</span></span>|  
|<span data-ttu-id="309ec-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-144">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-144">Int16</span></span>|  
|<span data-ttu-id="309ec-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-145">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-146">String</span><span class="sxs-lookup"><span data-stu-id="309ec-146">String</span></span>|  
|<span data-ttu-id="309ec-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="309ec-147">ASC_OR_DESC</span></span>|<span data-ttu-id="309ec-148">String</span><span class="sxs-lookup"><span data-stu-id="309ec-148">String</span></span>|  
|<span data-ttu-id="309ec-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="309ec-149">CARDINATLITY</span></span>|<span data-ttu-id="309ec-150">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-150">Int32</span></span>|  
|<span data-ttu-id="309ec-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="309ec-151">PAGES</span></span>|<span data-ttu-id="309ec-152">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-152">Int32</span></span>|  
|<span data-ttu-id="309ec-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="309ec-153">FILTER_CONDITION</span></span>|<span data-ttu-id="309ec-154">String</span><span class="sxs-lookup"><span data-stu-id="309ec-154">String</span></span>|  
|<span data-ttu-id="309ec-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="309ec-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="309ec-156">String</span><span class="sxs-lookup"><span data-stu-id="309ec-156">String</span></span>|  
|<span data-ttu-id="309ec-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="309ec-158">Byte</span><span class="sxs-lookup"><span data-stu-id="309ec-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="309ec-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="309ec-159">Columns</span></span>  
  
|<span data-ttu-id="309ec-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-160">ColumnName</span></span>|<span data-ttu-id="309ec-161">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="309ec-162">TABLE_CAT</span></span>|<span data-ttu-id="309ec-163">String</span><span class="sxs-lookup"><span data-stu-id="309ec-163">String</span></span>|  
|<span data-ttu-id="309ec-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309ec-164">TABLE_SCHEM</span></span>|<span data-ttu-id="309ec-165">String</span><span class="sxs-lookup"><span data-stu-id="309ec-165">String</span></span>|  
|<span data-ttu-id="309ec-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-166">TABLE_NAME</span></span>|<span data-ttu-id="309ec-167">String</span><span class="sxs-lookup"><span data-stu-id="309ec-167">String</span></span>|  
|<span data-ttu-id="309ec-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-168">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-169">String</span><span class="sxs-lookup"><span data-stu-id="309ec-169">String</span></span>|  
|<span data-ttu-id="309ec-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-170">DATA_TYPE</span></span>|<span data-ttu-id="309ec-171">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-171">Int16</span></span>|  
|<span data-ttu-id="309ec-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-172">TYPE_NAME</span></span>|<span data-ttu-id="309ec-173">String</span><span class="sxs-lookup"><span data-stu-id="309ec-173">String</span></span>|  
|<span data-ttu-id="309ec-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="309ec-174">COLUMN_SIZE</span></span>|<span data-ttu-id="309ec-175">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-175">Int32</span></span>|  
|<span data-ttu-id="309ec-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="309ec-177">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-177">Int32</span></span>|  
|<span data-ttu-id="309ec-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="309ec-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="309ec-179">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-179">Int16</span></span>|  
|<span data-ttu-id="309ec-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="309ec-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="309ec-181">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-181">Int16</span></span>|  
|<span data-ttu-id="309ec-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-182">NULLABLE</span></span>|<span data-ttu-id="309ec-183">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-183">Int16</span></span>|  
|<span data-ttu-id="309ec-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-184">REMARKS</span></span>|<span data-ttu-id="309ec-185">String</span><span class="sxs-lookup"><span data-stu-id="309ec-185">String</span></span>|  
|<span data-ttu-id="309ec-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="309ec-186">COLUMN_DEF</span></span>|<span data-ttu-id="309ec-187">String</span><span class="sxs-lookup"><span data-stu-id="309ec-187">String</span></span>|  
|<span data-ttu-id="309ec-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="309ec-189">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-189">Int16</span></span>|  
|<span data-ttu-id="309ec-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="309ec-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="309ec-191">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-191">Int16</span></span>|  
|<span data-ttu-id="309ec-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="309ec-193">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-193">Int32</span></span>|  
|<span data-ttu-id="309ec-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-195">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-195">Int32</span></span>|  
|<span data-ttu-id="309ec-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-196">IS_NULLABLE</span></span>|<span data-ttu-id="309ec-197">String</span><span class="sxs-lookup"><span data-stu-id="309ec-197">String</span></span>|  
|<span data-ttu-id="309ec-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="309ec-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="309ec-199">String</span><span class="sxs-lookup"><span data-stu-id="309ec-199">String</span></span>|  
|<span data-ttu-id="309ec-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="309ec-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="309ec-201">String</span><span class="sxs-lookup"><span data-stu-id="309ec-201">String</span></span>|  
|<span data-ttu-id="309ec-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="309ec-203">Byte</span><span class="sxs-lookup"><span data-stu-id="309ec-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="309ec-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="309ec-204">Procedures</span></span>  
  
|<span data-ttu-id="309ec-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-205">ColumnName</span></span>|<span data-ttu-id="309ec-206">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="309ec-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="309ec-208">String</span><span class="sxs-lookup"><span data-stu-id="309ec-208">String</span></span>|  
|<span data-ttu-id="309ec-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309ec-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="309ec-210">String</span><span class="sxs-lookup"><span data-stu-id="309ec-210">String</span></span>|  
|<span data-ttu-id="309ec-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="309ec-212">String</span><span class="sxs-lookup"><span data-stu-id="309ec-212">String</span></span>|  
|<span data-ttu-id="309ec-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309ec-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="309ec-214">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-214">Int32</span></span>|  
|<span data-ttu-id="309ec-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309ec-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="309ec-216">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-216">Int32</span></span>|  
|<span data-ttu-id="309ec-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="309ec-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="309ec-218">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-218">Int32</span></span>|  
|<span data-ttu-id="309ec-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-219">REMARKS</span></span>|<span data-ttu-id="309ec-220">String</span><span class="sxs-lookup"><span data-stu-id="309ec-220">String</span></span>|  
|<span data-ttu-id="309ec-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="309ec-222">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="309ec-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309ec-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="309ec-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-224">ColumnName</span></span>|<span data-ttu-id="309ec-225">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="309ec-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="309ec-227">String</span><span class="sxs-lookup"><span data-stu-id="309ec-227">String</span></span>|  
|<span data-ttu-id="309ec-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309ec-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="309ec-229">String</span><span class="sxs-lookup"><span data-stu-id="309ec-229">String</span></span>|  
|<span data-ttu-id="309ec-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="309ec-231">String</span><span class="sxs-lookup"><span data-stu-id="309ec-231">String</span></span>|  
|<span data-ttu-id="309ec-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-232">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-233">String</span><span class="sxs-lookup"><span data-stu-id="309ec-233">String</span></span>|  
|<span data-ttu-id="309ec-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-234">COLUMN_TYPE</span></span>|<span data-ttu-id="309ec-235">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-235">Int16</span></span>|  
|<span data-ttu-id="309ec-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-236">DATA_TYPE</span></span>|<span data-ttu-id="309ec-237">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-237">Int16</span></span>|  
|<span data-ttu-id="309ec-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-238">TYPE_NAME</span></span>|<span data-ttu-id="309ec-239">String</span><span class="sxs-lookup"><span data-stu-id="309ec-239">String</span></span>|  
|<span data-ttu-id="309ec-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="309ec-240">COLUMN_SIZE</span></span>|<span data-ttu-id="309ec-241">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-241">Int32</span></span>|  
|<span data-ttu-id="309ec-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="309ec-243">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-243">Int32</span></span>|  
|<span data-ttu-id="309ec-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="309ec-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="309ec-245">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-245">Int16</span></span>|  
|<span data-ttu-id="309ec-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="309ec-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="309ec-247">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-247">Int16</span></span>|  
|<span data-ttu-id="309ec-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-248">NULLABLE</span></span>|<span data-ttu-id="309ec-249">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-249">Int16</span></span>|  
|<span data-ttu-id="309ec-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-250">REMARKS</span></span>|<span data-ttu-id="309ec-251">String</span><span class="sxs-lookup"><span data-stu-id="309ec-251">String</span></span>|  
|<span data-ttu-id="309ec-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="309ec-252">COLUMN_DEF</span></span>|<span data-ttu-id="309ec-253">String</span><span class="sxs-lookup"><span data-stu-id="309ec-253">String</span></span>|  
|<span data-ttu-id="309ec-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="309ec-255">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-255">Int16</span></span>|  
|<span data-ttu-id="309ec-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="309ec-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="309ec-257">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-257">Int16</span></span>|  
|<span data-ttu-id="309ec-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="309ec-259">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-259">Int32</span></span>|  
|<span data-ttu-id="309ec-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-261">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-261">Int32</span></span>|  
|<span data-ttu-id="309ec-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-262">IS_NULLABLE</span></span>|<span data-ttu-id="309ec-263">String</span><span class="sxs-lookup"><span data-stu-id="309ec-263">String</span></span>|  
|<span data-ttu-id="309ec-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="309ec-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="309ec-265">String</span><span class="sxs-lookup"><span data-stu-id="309ec-265">String</span></span>|  
|<span data-ttu-id="309ec-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="309ec-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="309ec-267">String</span><span class="sxs-lookup"><span data-stu-id="309ec-267">String</span></span>|  
|<span data-ttu-id="309ec-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="309ec-269">Byte</span><span class="sxs-lookup"><span data-stu-id="309ec-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="309ec-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309ec-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="309ec-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-271">ColumnName</span></span>|<span data-ttu-id="309ec-272">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="309ec-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="309ec-274">String</span><span class="sxs-lookup"><span data-stu-id="309ec-274">String</span></span>|  
|<span data-ttu-id="309ec-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309ec-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="309ec-276">String</span><span class="sxs-lookup"><span data-stu-id="309ec-276">String</span></span>|  
|<span data-ttu-id="309ec-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="309ec-278">String</span><span class="sxs-lookup"><span data-stu-id="309ec-278">String</span></span>|  
|<span data-ttu-id="309ec-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-279">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-280">String</span><span class="sxs-lookup"><span data-stu-id="309ec-280">String</span></span>|  
|<span data-ttu-id="309ec-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-281">COLUMN_TYPE</span></span>|<span data-ttu-id="309ec-282">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-282">Int16</span></span>|  
|<span data-ttu-id="309ec-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-283">DATA_TYPE</span></span>|<span data-ttu-id="309ec-284">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-284">Int16</span></span>|  
|<span data-ttu-id="309ec-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-285">TYPE_NAME</span></span>|<span data-ttu-id="309ec-286">String</span><span class="sxs-lookup"><span data-stu-id="309ec-286">String</span></span>|  
|<span data-ttu-id="309ec-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="309ec-287">COLUMN_SIZE</span></span>|<span data-ttu-id="309ec-288">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-288">Int32</span></span>|  
|<span data-ttu-id="309ec-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="309ec-290">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-290">Int32</span></span>|  
|<span data-ttu-id="309ec-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="309ec-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="309ec-292">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-292">Int16</span></span>|  
|<span data-ttu-id="309ec-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="309ec-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="309ec-294">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-294">Int16</span></span>|  
|<span data-ttu-id="309ec-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-295">NULLABLE</span></span>|<span data-ttu-id="309ec-296">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-296">Int16</span></span>|  
|<span data-ttu-id="309ec-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-297">REMARKS</span></span>|<span data-ttu-id="309ec-298">String</span><span class="sxs-lookup"><span data-stu-id="309ec-298">String</span></span>|  
|<span data-ttu-id="309ec-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="309ec-299">COLUMN_DEF</span></span>|<span data-ttu-id="309ec-300">String</span><span class="sxs-lookup"><span data-stu-id="309ec-300">String</span></span>|  
|<span data-ttu-id="309ec-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="309ec-302">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-302">Int16</span></span>|  
|<span data-ttu-id="309ec-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="309ec-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="309ec-304">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-304">Int16</span></span>|  
|<span data-ttu-id="309ec-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="309ec-306">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-306">Int32</span></span>|  
|<span data-ttu-id="309ec-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-308">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-308">Int32</span></span>|  
|<span data-ttu-id="309ec-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-309">IS_NULLABLE</span></span>|<span data-ttu-id="309ec-310">String</span><span class="sxs-lookup"><span data-stu-id="309ec-310">String</span></span>|  
|<span data-ttu-id="309ec-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="309ec-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="309ec-312">String</span><span class="sxs-lookup"><span data-stu-id="309ec-312">String</span></span>|  
|<span data-ttu-id="309ec-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="309ec-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="309ec-314">String</span><span class="sxs-lookup"><span data-stu-id="309ec-314">String</span></span>|  
|<span data-ttu-id="309ec-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="309ec-316">Byte</span><span class="sxs-lookup"><span data-stu-id="309ec-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="309ec-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="309ec-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="309ec-318">El controlador ODBC de Oracle de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="309ec-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="309ec-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="309ec-319">Tables</span></span>  
  
-   <span data-ttu-id="309ec-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="309ec-320">Columns</span></span>  
  
-   <span data-ttu-id="309ec-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="309ec-321">Procedures</span></span>  
  
-   <span data-ttu-id="309ec-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309ec-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="309ec-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309ec-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="309ec-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="309ec-324">Views</span></span>  
  
-   <span data-ttu-id="309ec-325">Índices</span><span class="sxs-lookup"><span data-stu-id="309ec-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="309ec-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="309ec-326">Tables and Views</span></span>  
  
|<span data-ttu-id="309ec-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-327">ColumnName</span></span>|<span data-ttu-id="309ec-328">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="309ec-330">String</span><span class="sxs-lookup"><span data-stu-id="309ec-330">String</span></span>|  
|<span data-ttu-id="309ec-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309ec-331">TABLE_OWNER</span></span>|<span data-ttu-id="309ec-332">String</span><span class="sxs-lookup"><span data-stu-id="309ec-332">String</span></span>|  
|<span data-ttu-id="309ec-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-333">TABLE_NAME</span></span>|<span data-ttu-id="309ec-334">String</span><span class="sxs-lookup"><span data-stu-id="309ec-334">String</span></span>|  
|<span data-ttu-id="309ec-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-335">TABLE_TYPE</span></span>|<span data-ttu-id="309ec-336">String</span><span class="sxs-lookup"><span data-stu-id="309ec-336">String</span></span>|  
|<span data-ttu-id="309ec-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-337">REMARKS</span></span>|<span data-ttu-id="309ec-338">String</span><span class="sxs-lookup"><span data-stu-id="309ec-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="309ec-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="309ec-339">Columns</span></span>  
  
|<span data-ttu-id="309ec-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-340">ColumnName</span></span>|<span data-ttu-id="309ec-341">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="309ec-343">String</span><span class="sxs-lookup"><span data-stu-id="309ec-343">String</span></span>|  
|<span data-ttu-id="309ec-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309ec-344">TABLE_OWNER</span></span>|<span data-ttu-id="309ec-345">String</span><span class="sxs-lookup"><span data-stu-id="309ec-345">String</span></span>|  
|<span data-ttu-id="309ec-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-346">TABLE_NAME</span></span>|<span data-ttu-id="309ec-347">String</span><span class="sxs-lookup"><span data-stu-id="309ec-347">String</span></span>|  
|<span data-ttu-id="309ec-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-348">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-349">String</span><span class="sxs-lookup"><span data-stu-id="309ec-349">String</span></span>|  
|<span data-ttu-id="309ec-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-350">DATA_TYPE</span></span>|<span data-ttu-id="309ec-351">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-351">Int16</span></span>|  
|<span data-ttu-id="309ec-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-352">TYPE_NAME</span></span>|<span data-ttu-id="309ec-353">String</span><span class="sxs-lookup"><span data-stu-id="309ec-353">String</span></span>|  
|<span data-ttu-id="309ec-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="309ec-354">PRECISION</span></span>|<span data-ttu-id="309ec-355">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-355">Int32</span></span>|  
|<span data-ttu-id="309ec-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-356">LENGTH</span></span>|<span data-ttu-id="309ec-357">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-357">Int32</span></span>|  
|<span data-ttu-id="309ec-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="309ec-358">SCALE</span></span>|<span data-ttu-id="309ec-359">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-359">Int16</span></span>|  
|<span data-ttu-id="309ec-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="309ec-360">RADIX</span></span>|<span data-ttu-id="309ec-361">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-361">Int16</span></span>|  
|<span data-ttu-id="309ec-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-362">NULLABLE</span></span>|<span data-ttu-id="309ec-363">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-363">Int16</span></span>|  
|<span data-ttu-id="309ec-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-364">REMARKS</span></span>|<span data-ttu-id="309ec-365">String</span><span class="sxs-lookup"><span data-stu-id="309ec-365">String</span></span>|  
|<span data-ttu-id="309ec-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-367">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="309ec-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="309ec-368">Procedures</span></span>  
  
|<span data-ttu-id="309ec-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-369">ColumnName</span></span>|<span data-ttu-id="309ec-370">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="309ec-372">String</span><span class="sxs-lookup"><span data-stu-id="309ec-372">String</span></span>|  
|<span data-ttu-id="309ec-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309ec-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="309ec-374">String</span><span class="sxs-lookup"><span data-stu-id="309ec-374">String</span></span>|  
|<span data-ttu-id="309ec-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="309ec-376">String</span><span class="sxs-lookup"><span data-stu-id="309ec-376">String</span></span>|  
|<span data-ttu-id="309ec-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309ec-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="309ec-378">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-378">Int16</span></span>|  
|<span data-ttu-id="309ec-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309ec-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="309ec-380">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-380">Int16</span></span>|  
|<span data-ttu-id="309ec-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="309ec-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="309ec-382">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-382">Int16</span></span>|  
|<span data-ttu-id="309ec-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-383">REMARKS</span></span>|<span data-ttu-id="309ec-384">String</span><span class="sxs-lookup"><span data-stu-id="309ec-384">String</span></span>|  
|<span data-ttu-id="309ec-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="309ec-386">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="309ec-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309ec-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="309ec-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-388">ColumnName</span></span>|<span data-ttu-id="309ec-389">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="309ec-391">String</span><span class="sxs-lookup"><span data-stu-id="309ec-391">String</span></span>|  
|<span data-ttu-id="309ec-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309ec-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="309ec-393">String</span><span class="sxs-lookup"><span data-stu-id="309ec-393">String</span></span>|  
|<span data-ttu-id="309ec-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="309ec-395">String</span><span class="sxs-lookup"><span data-stu-id="309ec-395">String</span></span>|  
|<span data-ttu-id="309ec-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-396">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-397">String</span><span class="sxs-lookup"><span data-stu-id="309ec-397">String</span></span>|  
|<span data-ttu-id="309ec-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-398">COLUMN_TYPE</span></span>|<span data-ttu-id="309ec-399">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-399">Int16</span></span>|  
|<span data-ttu-id="309ec-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-400">DATA_TYPE</span></span>|<span data-ttu-id="309ec-401">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-401">Int16</span></span>|  
|<span data-ttu-id="309ec-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-402">TYPE_NAME</span></span>|<span data-ttu-id="309ec-403">String</span><span class="sxs-lookup"><span data-stu-id="309ec-403">String</span></span>|  
|<span data-ttu-id="309ec-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="309ec-404">PRECISION</span></span>|<span data-ttu-id="309ec-405">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-405">Int32</span></span>|  
|<span data-ttu-id="309ec-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-406">LENGTH</span></span>|<span data-ttu-id="309ec-407">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-407">Int32</span></span>|  
|<span data-ttu-id="309ec-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="309ec-408">SCALE</span></span>|<span data-ttu-id="309ec-409">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-409">Int16</span></span>|  
|<span data-ttu-id="309ec-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="309ec-410">RADIX</span></span>|<span data-ttu-id="309ec-411">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-411">Int16</span></span>|  
|<span data-ttu-id="309ec-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-412">NULLABLE</span></span>|<span data-ttu-id="309ec-413">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-413">Int16</span></span>|  
|<span data-ttu-id="309ec-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-414">REMARKS</span></span>|<span data-ttu-id="309ec-415">String</span><span class="sxs-lookup"><span data-stu-id="309ec-415">String</span></span>|  
|<span data-ttu-id="309ec-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="309ec-416">OVERLOAD</span></span>|<span data-ttu-id="309ec-417">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-417">Int32</span></span>|  
|<span data-ttu-id="309ec-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-419">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="309ec-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="309ec-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="309ec-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="309ec-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="309ec-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="309ec-422">Tables</span></span>  
  
-   <span data-ttu-id="309ec-423">Índices</span><span class="sxs-lookup"><span data-stu-id="309ec-423">Indexes</span></span>  
  
-   <span data-ttu-id="309ec-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="309ec-424">Columns</span></span>  
  
-   <span data-ttu-id="309ec-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="309ec-425">Procedures</span></span>  
  
-   <span data-ttu-id="309ec-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309ec-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="309ec-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309ec-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="309ec-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="309ec-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="309ec-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="309ec-429">Tables and Views</span></span>  
  
|<span data-ttu-id="309ec-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-430">ColumnName</span></span>|<span data-ttu-id="309ec-431">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="309ec-433">String</span><span class="sxs-lookup"><span data-stu-id="309ec-433">String</span></span>|  
|<span data-ttu-id="309ec-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309ec-434">TABLE_OWNER</span></span>|<span data-ttu-id="309ec-435">String</span><span class="sxs-lookup"><span data-stu-id="309ec-435">String</span></span>|  
|<span data-ttu-id="309ec-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-436">TABLE_NAME</span></span>|<span data-ttu-id="309ec-437">String</span><span class="sxs-lookup"><span data-stu-id="309ec-437">String</span></span>|  
|<span data-ttu-id="309ec-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-438">TABLE_TYPE</span></span>|<span data-ttu-id="309ec-439">String</span><span class="sxs-lookup"><span data-stu-id="309ec-439">String</span></span>|  
|<span data-ttu-id="309ec-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-440">REMARKS</span></span>|<span data-ttu-id="309ec-441">String</span><span class="sxs-lookup"><span data-stu-id="309ec-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="309ec-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="309ec-442">Columns</span></span>  
  
|<span data-ttu-id="309ec-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-443">ColumnName</span></span>|<span data-ttu-id="309ec-444">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="309ec-446">String</span><span class="sxs-lookup"><span data-stu-id="309ec-446">String</span></span>|  
|<span data-ttu-id="309ec-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309ec-447">TABLE_OWNER</span></span>|<span data-ttu-id="309ec-448">String</span><span class="sxs-lookup"><span data-stu-id="309ec-448">String</span></span>|  
|<span data-ttu-id="309ec-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-449">TABLE_NAME</span></span>|<span data-ttu-id="309ec-450">String</span><span class="sxs-lookup"><span data-stu-id="309ec-450">String</span></span>|  
|<span data-ttu-id="309ec-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-451">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-452">String</span><span class="sxs-lookup"><span data-stu-id="309ec-452">String</span></span>|  
|<span data-ttu-id="309ec-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-453">DATA_TYPE</span></span>|<span data-ttu-id="309ec-454">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-454">Int16</span></span>|  
|<span data-ttu-id="309ec-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-455">TYPE_NAME</span></span>|<span data-ttu-id="309ec-456">String</span><span class="sxs-lookup"><span data-stu-id="309ec-456">String</span></span>|  
|<span data-ttu-id="309ec-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="309ec-457">PRECISION</span></span>|<span data-ttu-id="309ec-458">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-458">Int32</span></span>|  
|<span data-ttu-id="309ec-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-459">LENGTH</span></span>|<span data-ttu-id="309ec-460">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-460">Int32</span></span>|  
|<span data-ttu-id="309ec-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="309ec-461">SCALE</span></span>|<span data-ttu-id="309ec-462">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-462">Int16</span></span>|  
|<span data-ttu-id="309ec-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="309ec-463">RADIX</span></span>|<span data-ttu-id="309ec-464">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-464">Int16</span></span>|  
|<span data-ttu-id="309ec-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-465">NULLABLE</span></span>|<span data-ttu-id="309ec-466">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-466">Int16</span></span>|  
|<span data-ttu-id="309ec-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-467">REMARKS</span></span>|<span data-ttu-id="309ec-468">String</span><span class="sxs-lookup"><span data-stu-id="309ec-468">String</span></span>|  
|<span data-ttu-id="309ec-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-470">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="309ec-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="309ec-471">Procedures</span></span>  
  
|<span data-ttu-id="309ec-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-472">ColumnName</span></span>|<span data-ttu-id="309ec-473">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="309ec-475">String</span><span class="sxs-lookup"><span data-stu-id="309ec-475">String</span></span>|  
|<span data-ttu-id="309ec-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309ec-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="309ec-477">String</span><span class="sxs-lookup"><span data-stu-id="309ec-477">String</span></span>|  
|<span data-ttu-id="309ec-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="309ec-479">String</span><span class="sxs-lookup"><span data-stu-id="309ec-479">String</span></span>|  
|<span data-ttu-id="309ec-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309ec-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="309ec-481">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-481">Int16</span></span>|  
|<span data-ttu-id="309ec-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="309ec-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="309ec-483">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-483">Int16</span></span>|  
|<span data-ttu-id="309ec-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="309ec-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="309ec-485">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-485">Int16</span></span>|  
|<span data-ttu-id="309ec-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-486">REMARKS</span></span>|<span data-ttu-id="309ec-487">String</span><span class="sxs-lookup"><span data-stu-id="309ec-487">String</span></span>|  
|<span data-ttu-id="309ec-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="309ec-489">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="309ec-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="309ec-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="309ec-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-491">ColumnName</span></span>|<span data-ttu-id="309ec-492">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="309ec-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="309ec-494">String</span><span class="sxs-lookup"><span data-stu-id="309ec-494">String</span></span>|  
|<span data-ttu-id="309ec-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="309ec-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="309ec-496">String</span><span class="sxs-lookup"><span data-stu-id="309ec-496">String</span></span>|  
|<span data-ttu-id="309ec-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="309ec-498">String</span><span class="sxs-lookup"><span data-stu-id="309ec-498">String</span></span>|  
|<span data-ttu-id="309ec-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-499">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-500">String</span><span class="sxs-lookup"><span data-stu-id="309ec-500">String</span></span>|  
|<span data-ttu-id="309ec-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-501">COLUMN_TYPE</span></span>|<span data-ttu-id="309ec-502">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-502">Int16</span></span>|  
|<span data-ttu-id="309ec-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-503">DATA_TYPE</span></span>|<span data-ttu-id="309ec-504">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-504">Int16</span></span>|  
|<span data-ttu-id="309ec-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-505">TYPE_NAME</span></span>|<span data-ttu-id="309ec-506">String</span><span class="sxs-lookup"><span data-stu-id="309ec-506">String</span></span>|  
|<span data-ttu-id="309ec-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="309ec-507">PRECISION</span></span>|<span data-ttu-id="309ec-508">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-508">Int32</span></span>|  
|<span data-ttu-id="309ec-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-509">LENGTH</span></span>|<span data-ttu-id="309ec-510">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-510">Int32</span></span>|  
|<span data-ttu-id="309ec-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="309ec-511">SCALE</span></span>|<span data-ttu-id="309ec-512">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-512">Int16</span></span>|  
|<span data-ttu-id="309ec-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="309ec-513">RADIX</span></span>|<span data-ttu-id="309ec-514">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-514">Int16</span></span>|  
|<span data-ttu-id="309ec-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-515">NULLABLE</span></span>|<span data-ttu-id="309ec-516">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-516">Int16</span></span>|  
|<span data-ttu-id="309ec-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-517">REMARKS</span></span>|<span data-ttu-id="309ec-518">String</span><span class="sxs-lookup"><span data-stu-id="309ec-518">String</span></span>|  
|<span data-ttu-id="309ec-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="309ec-519">OVERLOAD</span></span>|<span data-ttu-id="309ec-520">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-520">Int32</span></span>|  
|<span data-ttu-id="309ec-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-522">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="309ec-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="309ec-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="309ec-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="309ec-524">ColumnName</span></span>|<span data-ttu-id="309ec-525">DataType</span><span class="sxs-lookup"><span data-stu-id="309ec-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="309ec-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="309ec-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="309ec-527">String</span><span class="sxs-lookup"><span data-stu-id="309ec-527">String</span></span>|  
|<span data-ttu-id="309ec-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="309ec-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="309ec-529">String</span><span class="sxs-lookup"><span data-stu-id="309ec-529">String</span></span>|  
|<span data-ttu-id="309ec-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="309ec-531">String</span><span class="sxs-lookup"><span data-stu-id="309ec-531">String</span></span>|  
|<span data-ttu-id="309ec-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-532">COLUMN_NAME</span></span>|<span data-ttu-id="309ec-533">String</span><span class="sxs-lookup"><span data-stu-id="309ec-533">String</span></span>|  
|<span data-ttu-id="309ec-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-534">COLUMN_TYPE</span></span>|<span data-ttu-id="309ec-535">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-535">Int16</span></span>|  
|<span data-ttu-id="309ec-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-536">DATA_TYPE</span></span>|<span data-ttu-id="309ec-537">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-537">Int16</span></span>|  
|<span data-ttu-id="309ec-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="309ec-538">TYPE_NAME</span></span>|<span data-ttu-id="309ec-539">String</span><span class="sxs-lookup"><span data-stu-id="309ec-539">String</span></span>|  
|<span data-ttu-id="309ec-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="309ec-540">COLUMN_SIZE</span></span>|<span data-ttu-id="309ec-541">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-541">Int32</span></span>|  
|<span data-ttu-id="309ec-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="309ec-543">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-543">Int32</span></span>|  
|<span data-ttu-id="309ec-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="309ec-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="309ec-545">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-545">Int16</span></span>|  
|<span data-ttu-id="309ec-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="309ec-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="309ec-547">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-547">Int16</span></span>|  
|<span data-ttu-id="309ec-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-548">NULLABLE</span></span>|<span data-ttu-id="309ec-549">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-549">Int16</span></span>|  
|<span data-ttu-id="309ec-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="309ec-550">REMARKS</span></span>|<span data-ttu-id="309ec-551">String</span><span class="sxs-lookup"><span data-stu-id="309ec-551">String</span></span>|  
|<span data-ttu-id="309ec-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="309ec-552">COLUMN_DEF</span></span>|<span data-ttu-id="309ec-553">String</span><span class="sxs-lookup"><span data-stu-id="309ec-553">String</span></span>|  
|<span data-ttu-id="309ec-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="309ec-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="309ec-555">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-555">Int16</span></span>|  
|<span data-ttu-id="309ec-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="309ec-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="309ec-557">Int16</span><span class="sxs-lookup"><span data-stu-id="309ec-557">Int16</span></span>|  
|<span data-ttu-id="309ec-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="309ec-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="309ec-559">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-559">Int32</span></span>|  
|<span data-ttu-id="309ec-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="309ec-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="309ec-561">Int32</span><span class="sxs-lookup"><span data-stu-id="309ec-561">Int32</span></span>|  
|<span data-ttu-id="309ec-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="309ec-562">IS_NULLABLE</span></span>|<span data-ttu-id="309ec-563">String</span><span class="sxs-lookup"><span data-stu-id="309ec-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="309ec-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="309ec-564">See Also</span></span>  
 [<span data-ttu-id="309ec-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="309ec-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
