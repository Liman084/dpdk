# SPDX-License-Identifier: BSD-3-Clause
# Copyright(c) 2010-2014 Intel Corporation.
# Copyright(c) 2014 6WIND S.A.
# Copyright(c) Broadcom Limited.
# All rights reserved.

include $(RTE_SDK)/mk/rte.vars.mk

#
# library name
#
LIB = librte_pmd_bnxt.a

EXPORT_MAP := rte_pmd_bnxt_version.map

CFLAGS += -O3
CFLAGS += $(WERROR_FLAGS)
LDLIBS += -lrte_eal -lrte_mbuf -lrte_mempool -lrte_ring
LDLIBS += -lrte_ethdev -lrte_net -lrte_kvargs
LDLIBS += -lrte_bus_pci

EXPORT_MAP := rte_pmd_bnxt_version.map

#
# all source are stored in SRCS-y
#
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_cpr.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_ethdev.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_filter.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_flow.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_hwrm.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_ring.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_rxq.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_rxr.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_stats.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_txq.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_txr.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_vnic.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_irq.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_util.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += rte_pmd_bnxt.c
ifeq ($(CONFIG_RTE_ARCH_X86), y)
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += bnxt_rxtx_vec_sse.c
endif

ifeq ($(CONFIG_RTE_LIBRTE_BNXT_PMD), y)
CFLAGS += -I$(SRCDIR) -I$(SRCDIR)/tf_core -I$(SRCDIR)/tf_ulp
endif

SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/tf_core.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/bitalloc.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/tf_msg.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/rand.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/stack.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/tf_em.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/tf_rm.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/tf_tbl.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_core/tfp.c

SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/bnxt_ulp.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/ulp_mark_mgr.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/ulp_flow_db.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/ulp_template_db.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/ulp_utils.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/ulp_mapper.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/ulp_matcher.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/ulp_rte_parser.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/bnxt_ulp_flow.c
SRCS-$(CONFIG_RTE_LIBRTE_BNXT_PMD) += tf_ulp/ulp_port_db.c

#
# Export include files
#
SYMLINK-y-include +=
SYMLINK-$(CONFIG_RTE_LIBRTE_BNXT_PMD)-include := rte_pmd_bnxt.h

include $(RTE_SDK)/mk/rte.lib.mk
