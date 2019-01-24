---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 072a9cd365031cd5660d1824bc229d459abc5af8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525838"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="11d38-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="11d38-102">ODBC Schema Collections</span></span>
<span data-ttu-id="11d38-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="11d38-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="11d38-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="11d38-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="11d38-105">El controlador ODBC de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="11d38-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="11d38-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="11d38-106">Tables</span></span>  
  
-   <span data-ttu-id="11d38-107">Índices</span><span class="sxs-lookup"><span data-stu-id="11d38-107">Indexes</span></span>  
  
-   <span data-ttu-id="11d38-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="11d38-108">Columns</span></span>  
  
-   <span data-ttu-id="11d38-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="11d38-109">Procedures</span></span>  
  
-   <span data-ttu-id="11d38-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="11d38-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="11d38-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="11d38-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="11d38-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="11d38-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="11d38-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="11d38-113">Tables and Views</span></span>  
  
|<span data-ttu-id="11d38-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-114">ColumnName</span></span>|<span data-ttu-id="11d38-115">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="11d38-116">TABLE_CAT</span></span>|<span data-ttu-id="11d38-117">String</span><span class="sxs-lookup"><span data-stu-id="11d38-117">String</span></span>|  
|<span data-ttu-id="11d38-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="11d38-118">TABLE_SCHEM</span></span>|<span data-ttu-id="11d38-119">String</span><span class="sxs-lookup"><span data-stu-id="11d38-119">String</span></span>|  
|<span data-ttu-id="11d38-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-120">TABLE_NAME</span></span>|<span data-ttu-id="11d38-121">String</span><span class="sxs-lookup"><span data-stu-id="11d38-121">String</span></span>|  
|<span data-ttu-id="11d38-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-122">TABLE_TYPE</span></span>|<span data-ttu-id="11d38-123">String</span><span class="sxs-lookup"><span data-stu-id="11d38-123">String</span></span>|  
|<span data-ttu-id="11d38-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-124">REMARKS</span></span>|<span data-ttu-id="11d38-125">String</span><span class="sxs-lookup"><span data-stu-id="11d38-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="11d38-126">Índices</span><span class="sxs-lookup"><span data-stu-id="11d38-126">Indexes</span></span>  
  
|<span data-ttu-id="11d38-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-127">ColumnName</span></span>|<span data-ttu-id="11d38-128">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="11d38-129">TABLE_CAT</span></span>|<span data-ttu-id="11d38-130">String</span><span class="sxs-lookup"><span data-stu-id="11d38-130">String</span></span>|  
|<span data-ttu-id="11d38-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="11d38-131">TABLE_SCHEM</span></span>|<span data-ttu-id="11d38-132">String</span><span class="sxs-lookup"><span data-stu-id="11d38-132">String</span></span>|  
|<span data-ttu-id="11d38-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-133">TABLE_NAME</span></span>|<span data-ttu-id="11d38-134">String</span><span class="sxs-lookup"><span data-stu-id="11d38-134">String</span></span>|  
|<span data-ttu-id="11d38-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="11d38-135">NON_UNIQUE</span></span>|<span data-ttu-id="11d38-136">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-136">Int16</span></span>|  
|<span data-ttu-id="11d38-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="11d38-138">String</span><span class="sxs-lookup"><span data-stu-id="11d38-138">String</span></span>|  
|<span data-ttu-id="11d38-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-139">INDEX_NAME</span></span>|<span data-ttu-id="11d38-140">String</span><span class="sxs-lookup"><span data-stu-id="11d38-140">String</span></span>|  
|<span data-ttu-id="11d38-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-141">TYPE</span></span>|<span data-ttu-id="11d38-142">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-142">Int16</span></span>|  
|<span data-ttu-id="11d38-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-144">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-144">Int16</span></span>|  
|<span data-ttu-id="11d38-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-145">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-146">String</span><span class="sxs-lookup"><span data-stu-id="11d38-146">String</span></span>|  
|<span data-ttu-id="11d38-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="11d38-147">ASC_OR_DESC</span></span>|<span data-ttu-id="11d38-148">String</span><span class="sxs-lookup"><span data-stu-id="11d38-148">String</span></span>|  
|<span data-ttu-id="11d38-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="11d38-149">CARDINATLITY</span></span>|<span data-ttu-id="11d38-150">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-150">Int32</span></span>|  
|<span data-ttu-id="11d38-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="11d38-151">PAGES</span></span>|<span data-ttu-id="11d38-152">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-152">Int32</span></span>|  
|<span data-ttu-id="11d38-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="11d38-153">FILTER_CONDITION</span></span>|<span data-ttu-id="11d38-154">String</span><span class="sxs-lookup"><span data-stu-id="11d38-154">String</span></span>|  
|<span data-ttu-id="11d38-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="11d38-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="11d38-156">String</span><span class="sxs-lookup"><span data-stu-id="11d38-156">String</span></span>|  
|<span data-ttu-id="11d38-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="11d38-158">Byte</span><span class="sxs-lookup"><span data-stu-id="11d38-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="11d38-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="11d38-159">Columns</span></span>  
  
|<span data-ttu-id="11d38-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-160">ColumnName</span></span>|<span data-ttu-id="11d38-161">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="11d38-162">TABLE_CAT</span></span>|<span data-ttu-id="11d38-163">String</span><span class="sxs-lookup"><span data-stu-id="11d38-163">String</span></span>|  
|<span data-ttu-id="11d38-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="11d38-164">TABLE_SCHEM</span></span>|<span data-ttu-id="11d38-165">String</span><span class="sxs-lookup"><span data-stu-id="11d38-165">String</span></span>|  
|<span data-ttu-id="11d38-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-166">TABLE_NAME</span></span>|<span data-ttu-id="11d38-167">String</span><span class="sxs-lookup"><span data-stu-id="11d38-167">String</span></span>|  
|<span data-ttu-id="11d38-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-168">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-169">String</span><span class="sxs-lookup"><span data-stu-id="11d38-169">String</span></span>|  
|<span data-ttu-id="11d38-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-170">DATA_TYPE</span></span>|<span data-ttu-id="11d38-171">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-171">Int16</span></span>|  
|<span data-ttu-id="11d38-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-172">TYPE_NAME</span></span>|<span data-ttu-id="11d38-173">String</span><span class="sxs-lookup"><span data-stu-id="11d38-173">String</span></span>|  
|<span data-ttu-id="11d38-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="11d38-174">COLUMN_SIZE</span></span>|<span data-ttu-id="11d38-175">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-175">Int32</span></span>|  
|<span data-ttu-id="11d38-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="11d38-177">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-177">Int32</span></span>|  
|<span data-ttu-id="11d38-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="11d38-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="11d38-179">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-179">Int16</span></span>|  
|<span data-ttu-id="11d38-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="11d38-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="11d38-181">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-181">Int16</span></span>|  
|<span data-ttu-id="11d38-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-182">NULLABLE</span></span>|<span data-ttu-id="11d38-183">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-183">Int16</span></span>|  
|<span data-ttu-id="11d38-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-184">REMARKS</span></span>|<span data-ttu-id="11d38-185">String</span><span class="sxs-lookup"><span data-stu-id="11d38-185">String</span></span>|  
|<span data-ttu-id="11d38-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="11d38-186">COLUMN_DEF</span></span>|<span data-ttu-id="11d38-187">String</span><span class="sxs-lookup"><span data-stu-id="11d38-187">String</span></span>|  
|<span data-ttu-id="11d38-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="11d38-189">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-189">Int16</span></span>|  
|<span data-ttu-id="11d38-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="11d38-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="11d38-191">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-191">Int16</span></span>|  
|<span data-ttu-id="11d38-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="11d38-193">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-193">Int32</span></span>|  
|<span data-ttu-id="11d38-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-195">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-195">Int32</span></span>|  
|<span data-ttu-id="11d38-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-196">IS_NULLABLE</span></span>|<span data-ttu-id="11d38-197">String</span><span class="sxs-lookup"><span data-stu-id="11d38-197">String</span></span>|  
|<span data-ttu-id="11d38-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="11d38-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="11d38-199">String</span><span class="sxs-lookup"><span data-stu-id="11d38-199">String</span></span>|  
|<span data-ttu-id="11d38-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="11d38-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="11d38-201">String</span><span class="sxs-lookup"><span data-stu-id="11d38-201">String</span></span>|  
|<span data-ttu-id="11d38-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="11d38-203">Byte</span><span class="sxs-lookup"><span data-stu-id="11d38-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="11d38-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="11d38-204">Procedures</span></span>  
  
|<span data-ttu-id="11d38-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-205">ColumnName</span></span>|<span data-ttu-id="11d38-206">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="11d38-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="11d38-208">String</span><span class="sxs-lookup"><span data-stu-id="11d38-208">String</span></span>|  
|<span data-ttu-id="11d38-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="11d38-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="11d38-210">String</span><span class="sxs-lookup"><span data-stu-id="11d38-210">String</span></span>|  
|<span data-ttu-id="11d38-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="11d38-212">String</span><span class="sxs-lookup"><span data-stu-id="11d38-212">String</span></span>|  
|<span data-ttu-id="11d38-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="11d38-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="11d38-214">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-214">Int32</span></span>|  
|<span data-ttu-id="11d38-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="11d38-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="11d38-216">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-216">Int32</span></span>|  
|<span data-ttu-id="11d38-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="11d38-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="11d38-218">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-218">Int32</span></span>|  
|<span data-ttu-id="11d38-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-219">REMARKS</span></span>|<span data-ttu-id="11d38-220">String</span><span class="sxs-lookup"><span data-stu-id="11d38-220">String</span></span>|  
|<span data-ttu-id="11d38-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="11d38-222">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="11d38-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="11d38-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="11d38-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-224">ColumnName</span></span>|<span data-ttu-id="11d38-225">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="11d38-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="11d38-227">String</span><span class="sxs-lookup"><span data-stu-id="11d38-227">String</span></span>|  
|<span data-ttu-id="11d38-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="11d38-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="11d38-229">String</span><span class="sxs-lookup"><span data-stu-id="11d38-229">String</span></span>|  
|<span data-ttu-id="11d38-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="11d38-231">String</span><span class="sxs-lookup"><span data-stu-id="11d38-231">String</span></span>|  
|<span data-ttu-id="11d38-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-232">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-233">String</span><span class="sxs-lookup"><span data-stu-id="11d38-233">String</span></span>|  
|<span data-ttu-id="11d38-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-234">COLUMN_TYPE</span></span>|<span data-ttu-id="11d38-235">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-235">Int16</span></span>|  
|<span data-ttu-id="11d38-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-236">DATA_TYPE</span></span>|<span data-ttu-id="11d38-237">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-237">Int16</span></span>|  
|<span data-ttu-id="11d38-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-238">TYPE_NAME</span></span>|<span data-ttu-id="11d38-239">String</span><span class="sxs-lookup"><span data-stu-id="11d38-239">String</span></span>|  
|<span data-ttu-id="11d38-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="11d38-240">COLUMN_SIZE</span></span>|<span data-ttu-id="11d38-241">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-241">Int32</span></span>|  
|<span data-ttu-id="11d38-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="11d38-243">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-243">Int32</span></span>|  
|<span data-ttu-id="11d38-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="11d38-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="11d38-245">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-245">Int16</span></span>|  
|<span data-ttu-id="11d38-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="11d38-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="11d38-247">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-247">Int16</span></span>|  
|<span data-ttu-id="11d38-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-248">NULLABLE</span></span>|<span data-ttu-id="11d38-249">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-249">Int16</span></span>|  
|<span data-ttu-id="11d38-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-250">REMARKS</span></span>|<span data-ttu-id="11d38-251">String</span><span class="sxs-lookup"><span data-stu-id="11d38-251">String</span></span>|  
|<span data-ttu-id="11d38-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="11d38-252">COLUMN_DEF</span></span>|<span data-ttu-id="11d38-253">String</span><span class="sxs-lookup"><span data-stu-id="11d38-253">String</span></span>|  
|<span data-ttu-id="11d38-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="11d38-255">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-255">Int16</span></span>|  
|<span data-ttu-id="11d38-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="11d38-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="11d38-257">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-257">Int16</span></span>|  
|<span data-ttu-id="11d38-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="11d38-259">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-259">Int32</span></span>|  
|<span data-ttu-id="11d38-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-261">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-261">Int32</span></span>|  
|<span data-ttu-id="11d38-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-262">IS_NULLABLE</span></span>|<span data-ttu-id="11d38-263">String</span><span class="sxs-lookup"><span data-stu-id="11d38-263">String</span></span>|  
|<span data-ttu-id="11d38-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="11d38-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="11d38-265">String</span><span class="sxs-lookup"><span data-stu-id="11d38-265">String</span></span>|  
|<span data-ttu-id="11d38-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="11d38-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="11d38-267">String</span><span class="sxs-lookup"><span data-stu-id="11d38-267">String</span></span>|  
|<span data-ttu-id="11d38-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="11d38-269">Byte</span><span class="sxs-lookup"><span data-stu-id="11d38-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="11d38-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="11d38-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="11d38-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-271">ColumnName</span></span>|<span data-ttu-id="11d38-272">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="11d38-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="11d38-274">String</span><span class="sxs-lookup"><span data-stu-id="11d38-274">String</span></span>|  
|<span data-ttu-id="11d38-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="11d38-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="11d38-276">String</span><span class="sxs-lookup"><span data-stu-id="11d38-276">String</span></span>|  
|<span data-ttu-id="11d38-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="11d38-278">String</span><span class="sxs-lookup"><span data-stu-id="11d38-278">String</span></span>|  
|<span data-ttu-id="11d38-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-279">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-280">String</span><span class="sxs-lookup"><span data-stu-id="11d38-280">String</span></span>|  
|<span data-ttu-id="11d38-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-281">COLUMN_TYPE</span></span>|<span data-ttu-id="11d38-282">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-282">Int16</span></span>|  
|<span data-ttu-id="11d38-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-283">DATA_TYPE</span></span>|<span data-ttu-id="11d38-284">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-284">Int16</span></span>|  
|<span data-ttu-id="11d38-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-285">TYPE_NAME</span></span>|<span data-ttu-id="11d38-286">String</span><span class="sxs-lookup"><span data-stu-id="11d38-286">String</span></span>|  
|<span data-ttu-id="11d38-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="11d38-287">COLUMN_SIZE</span></span>|<span data-ttu-id="11d38-288">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-288">Int32</span></span>|  
|<span data-ttu-id="11d38-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="11d38-290">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-290">Int32</span></span>|  
|<span data-ttu-id="11d38-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="11d38-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="11d38-292">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-292">Int16</span></span>|  
|<span data-ttu-id="11d38-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="11d38-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="11d38-294">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-294">Int16</span></span>|  
|<span data-ttu-id="11d38-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-295">NULLABLE</span></span>|<span data-ttu-id="11d38-296">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-296">Int16</span></span>|  
|<span data-ttu-id="11d38-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-297">REMARKS</span></span>|<span data-ttu-id="11d38-298">String</span><span class="sxs-lookup"><span data-stu-id="11d38-298">String</span></span>|  
|<span data-ttu-id="11d38-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="11d38-299">COLUMN_DEF</span></span>|<span data-ttu-id="11d38-300">String</span><span class="sxs-lookup"><span data-stu-id="11d38-300">String</span></span>|  
|<span data-ttu-id="11d38-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="11d38-302">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-302">Int16</span></span>|  
|<span data-ttu-id="11d38-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="11d38-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="11d38-304">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-304">Int16</span></span>|  
|<span data-ttu-id="11d38-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="11d38-306">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-306">Int32</span></span>|  
|<span data-ttu-id="11d38-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-308">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-308">Int32</span></span>|  
|<span data-ttu-id="11d38-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-309">IS_NULLABLE</span></span>|<span data-ttu-id="11d38-310">String</span><span class="sxs-lookup"><span data-stu-id="11d38-310">String</span></span>|  
|<span data-ttu-id="11d38-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="11d38-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="11d38-312">String</span><span class="sxs-lookup"><span data-stu-id="11d38-312">String</span></span>|  
|<span data-ttu-id="11d38-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="11d38-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="11d38-314">String</span><span class="sxs-lookup"><span data-stu-id="11d38-314">String</span></span>|  
|<span data-ttu-id="11d38-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="11d38-316">Byte</span><span class="sxs-lookup"><span data-stu-id="11d38-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="11d38-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="11d38-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="11d38-318">El controlador ODBC de Oracle de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="11d38-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="11d38-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="11d38-319">Tables</span></span>  
  
-   <span data-ttu-id="11d38-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="11d38-320">Columns</span></span>  
  
-   <span data-ttu-id="11d38-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="11d38-321">Procedures</span></span>  
  
-   <span data-ttu-id="11d38-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="11d38-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="11d38-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="11d38-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="11d38-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="11d38-324">Views</span></span>  
  
-   <span data-ttu-id="11d38-325">Índices</span><span class="sxs-lookup"><span data-stu-id="11d38-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="11d38-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="11d38-326">Tables and Views</span></span>  
  
|<span data-ttu-id="11d38-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-327">ColumnName</span></span>|<span data-ttu-id="11d38-328">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="11d38-330">String</span><span class="sxs-lookup"><span data-stu-id="11d38-330">String</span></span>|  
|<span data-ttu-id="11d38-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="11d38-331">TABLE_OWNER</span></span>|<span data-ttu-id="11d38-332">String</span><span class="sxs-lookup"><span data-stu-id="11d38-332">String</span></span>|  
|<span data-ttu-id="11d38-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-333">TABLE_NAME</span></span>|<span data-ttu-id="11d38-334">String</span><span class="sxs-lookup"><span data-stu-id="11d38-334">String</span></span>|  
|<span data-ttu-id="11d38-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-335">TABLE_TYPE</span></span>|<span data-ttu-id="11d38-336">String</span><span class="sxs-lookup"><span data-stu-id="11d38-336">String</span></span>|  
|<span data-ttu-id="11d38-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-337">REMARKS</span></span>|<span data-ttu-id="11d38-338">String</span><span class="sxs-lookup"><span data-stu-id="11d38-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="11d38-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="11d38-339">Columns</span></span>  
  
|<span data-ttu-id="11d38-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-340">ColumnName</span></span>|<span data-ttu-id="11d38-341">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="11d38-343">String</span><span class="sxs-lookup"><span data-stu-id="11d38-343">String</span></span>|  
|<span data-ttu-id="11d38-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="11d38-344">TABLE_OWNER</span></span>|<span data-ttu-id="11d38-345">String</span><span class="sxs-lookup"><span data-stu-id="11d38-345">String</span></span>|  
|<span data-ttu-id="11d38-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-346">TABLE_NAME</span></span>|<span data-ttu-id="11d38-347">String</span><span class="sxs-lookup"><span data-stu-id="11d38-347">String</span></span>|  
|<span data-ttu-id="11d38-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-348">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-349">String</span><span class="sxs-lookup"><span data-stu-id="11d38-349">String</span></span>|  
|<span data-ttu-id="11d38-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-350">DATA_TYPE</span></span>|<span data-ttu-id="11d38-351">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-351">Int16</span></span>|  
|<span data-ttu-id="11d38-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-352">TYPE_NAME</span></span>|<span data-ttu-id="11d38-353">String</span><span class="sxs-lookup"><span data-stu-id="11d38-353">String</span></span>|  
|<span data-ttu-id="11d38-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="11d38-354">PRECISION</span></span>|<span data-ttu-id="11d38-355">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-355">Int32</span></span>|  
|<span data-ttu-id="11d38-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-356">LENGTH</span></span>|<span data-ttu-id="11d38-357">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-357">Int32</span></span>|  
|<span data-ttu-id="11d38-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="11d38-358">SCALE</span></span>|<span data-ttu-id="11d38-359">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-359">Int16</span></span>|  
|<span data-ttu-id="11d38-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="11d38-360">RADIX</span></span>|<span data-ttu-id="11d38-361">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-361">Int16</span></span>|  
|<span data-ttu-id="11d38-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-362">NULLABLE</span></span>|<span data-ttu-id="11d38-363">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-363">Int16</span></span>|  
|<span data-ttu-id="11d38-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-364">REMARKS</span></span>|<span data-ttu-id="11d38-365">String</span><span class="sxs-lookup"><span data-stu-id="11d38-365">String</span></span>|  
|<span data-ttu-id="11d38-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-367">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="11d38-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="11d38-368">Procedures</span></span>  
  
|<span data-ttu-id="11d38-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-369">ColumnName</span></span>|<span data-ttu-id="11d38-370">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="11d38-372">String</span><span class="sxs-lookup"><span data-stu-id="11d38-372">String</span></span>|  
|<span data-ttu-id="11d38-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="11d38-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="11d38-374">String</span><span class="sxs-lookup"><span data-stu-id="11d38-374">String</span></span>|  
|<span data-ttu-id="11d38-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="11d38-376">String</span><span class="sxs-lookup"><span data-stu-id="11d38-376">String</span></span>|  
|<span data-ttu-id="11d38-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="11d38-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="11d38-378">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-378">Int16</span></span>|  
|<span data-ttu-id="11d38-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="11d38-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="11d38-380">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-380">Int16</span></span>|  
|<span data-ttu-id="11d38-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="11d38-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="11d38-382">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-382">Int16</span></span>|  
|<span data-ttu-id="11d38-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-383">REMARKS</span></span>|<span data-ttu-id="11d38-384">String</span><span class="sxs-lookup"><span data-stu-id="11d38-384">String</span></span>|  
|<span data-ttu-id="11d38-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="11d38-386">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="11d38-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="11d38-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="11d38-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-388">ColumnName</span></span>|<span data-ttu-id="11d38-389">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="11d38-391">String</span><span class="sxs-lookup"><span data-stu-id="11d38-391">String</span></span>|  
|<span data-ttu-id="11d38-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="11d38-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="11d38-393">String</span><span class="sxs-lookup"><span data-stu-id="11d38-393">String</span></span>|  
|<span data-ttu-id="11d38-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="11d38-395">String</span><span class="sxs-lookup"><span data-stu-id="11d38-395">String</span></span>|  
|<span data-ttu-id="11d38-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-396">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-397">String</span><span class="sxs-lookup"><span data-stu-id="11d38-397">String</span></span>|  
|<span data-ttu-id="11d38-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-398">COLUMN_TYPE</span></span>|<span data-ttu-id="11d38-399">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-399">Int16</span></span>|  
|<span data-ttu-id="11d38-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-400">DATA_TYPE</span></span>|<span data-ttu-id="11d38-401">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-401">Int16</span></span>|  
|<span data-ttu-id="11d38-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-402">TYPE_NAME</span></span>|<span data-ttu-id="11d38-403">String</span><span class="sxs-lookup"><span data-stu-id="11d38-403">String</span></span>|  
|<span data-ttu-id="11d38-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="11d38-404">PRECISION</span></span>|<span data-ttu-id="11d38-405">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-405">Int32</span></span>|  
|<span data-ttu-id="11d38-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-406">LENGTH</span></span>|<span data-ttu-id="11d38-407">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-407">Int32</span></span>|  
|<span data-ttu-id="11d38-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="11d38-408">SCALE</span></span>|<span data-ttu-id="11d38-409">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-409">Int16</span></span>|  
|<span data-ttu-id="11d38-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="11d38-410">RADIX</span></span>|<span data-ttu-id="11d38-411">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-411">Int16</span></span>|  
|<span data-ttu-id="11d38-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-412">NULLABLE</span></span>|<span data-ttu-id="11d38-413">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-413">Int16</span></span>|  
|<span data-ttu-id="11d38-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-414">REMARKS</span></span>|<span data-ttu-id="11d38-415">String</span><span class="sxs-lookup"><span data-stu-id="11d38-415">String</span></span>|  
|<span data-ttu-id="11d38-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="11d38-416">OVERLOAD</span></span>|<span data-ttu-id="11d38-417">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-417">Int32</span></span>|  
|<span data-ttu-id="11d38-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-419">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="11d38-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="11d38-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="11d38-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="11d38-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="11d38-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="11d38-422">Tables</span></span>  
  
-   <span data-ttu-id="11d38-423">Índices</span><span class="sxs-lookup"><span data-stu-id="11d38-423">Indexes</span></span>  
  
-   <span data-ttu-id="11d38-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="11d38-424">Columns</span></span>  
  
-   <span data-ttu-id="11d38-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="11d38-425">Procedures</span></span>  
  
-   <span data-ttu-id="11d38-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="11d38-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="11d38-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="11d38-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="11d38-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="11d38-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="11d38-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="11d38-429">Tables and Views</span></span>  
  
|<span data-ttu-id="11d38-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-430">ColumnName</span></span>|<span data-ttu-id="11d38-431">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="11d38-433">String</span><span class="sxs-lookup"><span data-stu-id="11d38-433">String</span></span>|  
|<span data-ttu-id="11d38-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="11d38-434">TABLE_OWNER</span></span>|<span data-ttu-id="11d38-435">String</span><span class="sxs-lookup"><span data-stu-id="11d38-435">String</span></span>|  
|<span data-ttu-id="11d38-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-436">TABLE_NAME</span></span>|<span data-ttu-id="11d38-437">String</span><span class="sxs-lookup"><span data-stu-id="11d38-437">String</span></span>|  
|<span data-ttu-id="11d38-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-438">TABLE_TYPE</span></span>|<span data-ttu-id="11d38-439">String</span><span class="sxs-lookup"><span data-stu-id="11d38-439">String</span></span>|  
|<span data-ttu-id="11d38-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-440">REMARKS</span></span>|<span data-ttu-id="11d38-441">String</span><span class="sxs-lookup"><span data-stu-id="11d38-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="11d38-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="11d38-442">Columns</span></span>  
  
|<span data-ttu-id="11d38-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-443">ColumnName</span></span>|<span data-ttu-id="11d38-444">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="11d38-446">String</span><span class="sxs-lookup"><span data-stu-id="11d38-446">String</span></span>|  
|<span data-ttu-id="11d38-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="11d38-447">TABLE_OWNER</span></span>|<span data-ttu-id="11d38-448">String</span><span class="sxs-lookup"><span data-stu-id="11d38-448">String</span></span>|  
|<span data-ttu-id="11d38-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-449">TABLE_NAME</span></span>|<span data-ttu-id="11d38-450">String</span><span class="sxs-lookup"><span data-stu-id="11d38-450">String</span></span>|  
|<span data-ttu-id="11d38-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-451">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-452">String</span><span class="sxs-lookup"><span data-stu-id="11d38-452">String</span></span>|  
|<span data-ttu-id="11d38-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-453">DATA_TYPE</span></span>|<span data-ttu-id="11d38-454">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-454">Int16</span></span>|  
|<span data-ttu-id="11d38-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-455">TYPE_NAME</span></span>|<span data-ttu-id="11d38-456">String</span><span class="sxs-lookup"><span data-stu-id="11d38-456">String</span></span>|  
|<span data-ttu-id="11d38-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="11d38-457">PRECISION</span></span>|<span data-ttu-id="11d38-458">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-458">Int32</span></span>|  
|<span data-ttu-id="11d38-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-459">LENGTH</span></span>|<span data-ttu-id="11d38-460">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-460">Int32</span></span>|  
|<span data-ttu-id="11d38-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="11d38-461">SCALE</span></span>|<span data-ttu-id="11d38-462">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-462">Int16</span></span>|  
|<span data-ttu-id="11d38-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="11d38-463">RADIX</span></span>|<span data-ttu-id="11d38-464">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-464">Int16</span></span>|  
|<span data-ttu-id="11d38-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-465">NULLABLE</span></span>|<span data-ttu-id="11d38-466">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-466">Int16</span></span>|  
|<span data-ttu-id="11d38-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-467">REMARKS</span></span>|<span data-ttu-id="11d38-468">String</span><span class="sxs-lookup"><span data-stu-id="11d38-468">String</span></span>|  
|<span data-ttu-id="11d38-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-470">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="11d38-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="11d38-471">Procedures</span></span>  
  
|<span data-ttu-id="11d38-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-472">ColumnName</span></span>|<span data-ttu-id="11d38-473">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="11d38-475">String</span><span class="sxs-lookup"><span data-stu-id="11d38-475">String</span></span>|  
|<span data-ttu-id="11d38-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="11d38-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="11d38-477">String</span><span class="sxs-lookup"><span data-stu-id="11d38-477">String</span></span>|  
|<span data-ttu-id="11d38-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="11d38-479">String</span><span class="sxs-lookup"><span data-stu-id="11d38-479">String</span></span>|  
|<span data-ttu-id="11d38-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="11d38-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="11d38-481">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-481">Int16</span></span>|  
|<span data-ttu-id="11d38-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="11d38-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="11d38-483">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-483">Int16</span></span>|  
|<span data-ttu-id="11d38-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="11d38-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="11d38-485">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-485">Int16</span></span>|  
|<span data-ttu-id="11d38-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-486">REMARKS</span></span>|<span data-ttu-id="11d38-487">String</span><span class="sxs-lookup"><span data-stu-id="11d38-487">String</span></span>|  
|<span data-ttu-id="11d38-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="11d38-489">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="11d38-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="11d38-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="11d38-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-491">ColumnName</span></span>|<span data-ttu-id="11d38-492">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="11d38-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="11d38-494">String</span><span class="sxs-lookup"><span data-stu-id="11d38-494">String</span></span>|  
|<span data-ttu-id="11d38-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="11d38-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="11d38-496">String</span><span class="sxs-lookup"><span data-stu-id="11d38-496">String</span></span>|  
|<span data-ttu-id="11d38-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="11d38-498">String</span><span class="sxs-lookup"><span data-stu-id="11d38-498">String</span></span>|  
|<span data-ttu-id="11d38-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-499">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-500">String</span><span class="sxs-lookup"><span data-stu-id="11d38-500">String</span></span>|  
|<span data-ttu-id="11d38-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-501">COLUMN_TYPE</span></span>|<span data-ttu-id="11d38-502">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-502">Int16</span></span>|  
|<span data-ttu-id="11d38-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-503">DATA_TYPE</span></span>|<span data-ttu-id="11d38-504">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-504">Int16</span></span>|  
|<span data-ttu-id="11d38-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-505">TYPE_NAME</span></span>|<span data-ttu-id="11d38-506">String</span><span class="sxs-lookup"><span data-stu-id="11d38-506">String</span></span>|  
|<span data-ttu-id="11d38-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="11d38-507">PRECISION</span></span>|<span data-ttu-id="11d38-508">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-508">Int32</span></span>|  
|<span data-ttu-id="11d38-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-509">LENGTH</span></span>|<span data-ttu-id="11d38-510">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-510">Int32</span></span>|  
|<span data-ttu-id="11d38-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="11d38-511">SCALE</span></span>|<span data-ttu-id="11d38-512">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-512">Int16</span></span>|  
|<span data-ttu-id="11d38-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="11d38-513">RADIX</span></span>|<span data-ttu-id="11d38-514">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-514">Int16</span></span>|  
|<span data-ttu-id="11d38-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-515">NULLABLE</span></span>|<span data-ttu-id="11d38-516">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-516">Int16</span></span>|  
|<span data-ttu-id="11d38-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-517">REMARKS</span></span>|<span data-ttu-id="11d38-518">String</span><span class="sxs-lookup"><span data-stu-id="11d38-518">String</span></span>|  
|<span data-ttu-id="11d38-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="11d38-519">OVERLOAD</span></span>|<span data-ttu-id="11d38-520">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-520">Int32</span></span>|  
|<span data-ttu-id="11d38-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-522">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="11d38-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="11d38-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="11d38-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="11d38-524">ColumnName</span></span>|<span data-ttu-id="11d38-525">DataType</span><span class="sxs-lookup"><span data-stu-id="11d38-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="11d38-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="11d38-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="11d38-527">String</span><span class="sxs-lookup"><span data-stu-id="11d38-527">String</span></span>|  
|<span data-ttu-id="11d38-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="11d38-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="11d38-529">String</span><span class="sxs-lookup"><span data-stu-id="11d38-529">String</span></span>|  
|<span data-ttu-id="11d38-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="11d38-531">String</span><span class="sxs-lookup"><span data-stu-id="11d38-531">String</span></span>|  
|<span data-ttu-id="11d38-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-532">COLUMN_NAME</span></span>|<span data-ttu-id="11d38-533">String</span><span class="sxs-lookup"><span data-stu-id="11d38-533">String</span></span>|  
|<span data-ttu-id="11d38-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-534">COLUMN_TYPE</span></span>|<span data-ttu-id="11d38-535">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-535">Int16</span></span>|  
|<span data-ttu-id="11d38-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-536">DATA_TYPE</span></span>|<span data-ttu-id="11d38-537">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-537">Int16</span></span>|  
|<span data-ttu-id="11d38-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="11d38-538">TYPE_NAME</span></span>|<span data-ttu-id="11d38-539">String</span><span class="sxs-lookup"><span data-stu-id="11d38-539">String</span></span>|  
|<span data-ttu-id="11d38-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="11d38-540">COLUMN_SIZE</span></span>|<span data-ttu-id="11d38-541">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-541">Int32</span></span>|  
|<span data-ttu-id="11d38-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="11d38-543">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-543">Int32</span></span>|  
|<span data-ttu-id="11d38-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="11d38-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="11d38-545">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-545">Int16</span></span>|  
|<span data-ttu-id="11d38-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="11d38-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="11d38-547">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-547">Int16</span></span>|  
|<span data-ttu-id="11d38-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-548">NULLABLE</span></span>|<span data-ttu-id="11d38-549">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-549">Int16</span></span>|  
|<span data-ttu-id="11d38-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="11d38-550">REMARKS</span></span>|<span data-ttu-id="11d38-551">String</span><span class="sxs-lookup"><span data-stu-id="11d38-551">String</span></span>|  
|<span data-ttu-id="11d38-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="11d38-552">COLUMN_DEF</span></span>|<span data-ttu-id="11d38-553">String</span><span class="sxs-lookup"><span data-stu-id="11d38-553">String</span></span>|  
|<span data-ttu-id="11d38-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="11d38-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="11d38-555">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-555">Int16</span></span>|  
|<span data-ttu-id="11d38-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="11d38-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="11d38-557">Int16</span><span class="sxs-lookup"><span data-stu-id="11d38-557">Int16</span></span>|  
|<span data-ttu-id="11d38-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="11d38-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="11d38-559">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-559">Int32</span></span>|  
|<span data-ttu-id="11d38-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="11d38-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="11d38-561">Int32</span><span class="sxs-lookup"><span data-stu-id="11d38-561">Int32</span></span>|  
|<span data-ttu-id="11d38-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="11d38-562">IS_NULLABLE</span></span>|<span data-ttu-id="11d38-563">String</span><span class="sxs-lookup"><span data-stu-id="11d38-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11d38-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="11d38-564">See also</span></span>
- [<span data-ttu-id="11d38-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="11d38-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
