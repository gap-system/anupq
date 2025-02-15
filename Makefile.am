ACLOCAL_AMFLAGS = -I m4

BINARCHDIR = bin/$(GAPARCH)

#
# The following are valid compilation flags for the program.
#
#STANDARD_PCP -- if compiling version which permits construction of
#                standard presentation
#
#GAP_LINK  -- GAP is called by pq to perform insoluble stabiliser calculations 
#
#GAP -- if compiling version for incorporation in GAP
#
#DEBUG -- debugging information is generated by a number of procedures
#
# Change features of executable
#
#RUN_TIME -- supply maximum number of defining generators and class bound 
#             at run-time  (see README file for further details)
#
#TAILS_FILTER -- apply filter for exponent 4 and 5 and max occurrences
#
#CONSISTENCY_FILTER -- apply filter for exponent 4 and 5 and max occurrences
#
#
PQFLAGS = -DGAP_LINK_VIA_FILE -DGAP -DSTANDARD_PCP -DGROUP

PQFLAGS += -DANUPQ_GAP_EXEC='"@GAP_EXEC@"'

bin_PROGRAMS = pq

pq_LDFLAGS = $(GMP_LDFLAGS)
pq_LDADD = $(GMP_LIBS)
pq_CPPFLAGS = $(GMP_CPPFLAGS) $(PQFLAGS)

pq_CFLAGS = -Wall -Wextra -Wno-unused-parameter

pq_SOURCES = \
    src/AllocateSpace.c \
    src/CloseFile.c \
    src/Extend_Auts.c \
    src/FreeSpace.c \
    src/GAP.c \
    src/GAP_link_via_file.c \
    src/GAP_present.c \
    src/OpenFile.c \
    src/TemporaryFile.c \
    src/action.c \
    src/assemble_matrix.c \
    src/autgp_order.c \
    src/calculate_jacobi.c \
    src/central_auts.c \
    src/check_exponent.c \
    src/class1_eliminate.c \
    src/close_relations.c \
    src/close_subgroup.c \
    src/collect.c \
    src/collect_comm.c \
    src/collect_gen_word.c \
    src/collect_relations.c \
    src/collect_word.c \
    src/collectp2.c \
    src/commutator.c \
    src/commute_dgen.c \
    src/compact.c \
    src/compact_description.c \
    src/consistency.c \
    src/consistency_filter.c \
    src/consistency_info.c \
    src/construct.c \
    src/convert.c \
    src/defaults_pga.c \
    src/degree.c \
    src/delete_tables.c \
    src/down_class.c \
    src/echelon.c \
    src/echelonise_matrix.c \
    src/eliminate.c \
    src/expand_commutator.c \
    src/exponent_auts.c \
    src/exponent_info.c \
    src/extend_automorphisms.c \
    src/extend_matrix.c \
    src/extend_representation.c \
    src/extra_relations.c \
    src/find_allowable_subgroup.c \
    src/find_image.c \
    src/find_permutation.c \
    src/formula.c \
    src/generator_definition.c \
    src/get_definition_sets.c \
    src/identity.c \
    src/immediate_descendant.c \
    src/initialise_pcp.c \
    src/initialise_pga.c \
    src/insoluble_orbits.c \
    src/int_power.c \
    src/interactive_pga.c \
    src/interactive_pq.c \
    src/invert.c \
    src/invert_auts.c \
    src/invert_modp.c \
    src/is_genlim_exceeded.c \
    src/is_space_exhausted.c \
    src/isom_options.c \
    src/iteration.c \
    src/jacobi.c \
    src/label_to_subgroup.c \
    src/last_class.c \
    src/list_commutators.c \
    src/map_relations.c \
    src/matrix.c \
    src/maxoccur.c \
    src/multiply_word.c \
    src/next_class.c \
    src/options.c \
    src/orbit_summary.c \
    src/permute_elements.c \
    src/permute_subgroups.c \
    src/pgroup.c \
    src/power.c \
    src/pquotient.c \
    src/pretty_filter.c \
    src/pretty_filterfns.c \
    src/print_arrays.c \
    src/print_auts.c \
    src/print_level.c \
    src/print_multiweight.c \
    src/print_presentation.c \
    src/print_structure.c \
    src/print_word.c \
    src/read.c \
    src/read_auts.c \
    src/read_parameters.c \
    src/read_relations.c \
    src/read_relator_file.c \
    src/read_value.c \
    src/read_word.c \
    src/reduce_matrix.c \
    src/reduced_covers.c \
    src/report_error.c \
    src/restore_group.c \
    src/setup.c \
    src/setup_reps.c \
    src/soluble_orbits.c \
    src/solve_equation.c \
    src/stabiliser.c \
    src/stages.c \
    src/standard.c \
    src/start_group.c \
    src/start_iteration.c \
    src/step_range.c \
    src/store_definition_sets.c \
    src/strip_identities.c \
    src/subgroup_to_label.c \
    src/system.c \
    src/tail_info.c \
    src/tails.c \
    src/tails_filter.c \
    src/text.c \
    src/update.c \
    src/update_generators.c \
    src/update_name.c \
    src/write.c \
    src/main.c


all-local: pq$(EXEEXT)
	$(mkdir_p) $(top_srcdir)/$(BINARCHDIR)
	rm -f $(abs_top_srcdir)/$(BINARCHDIR)/pq$(EXEEXT)
	cp pq$(EXEEXT) $(abs_top_srcdir)/$(BINARCHDIR)
	@echo "SUCCESS!"

clean-local:
	rm -rf $(BINARCHDIR)
	(cd doc && rm -f *.aux *.bbl *.blg *.brf *.idx *.ilg *.ind *.log *.out *.pnr *.toc)
	(cd standalone-doc && rm -rf *.aux *.log *.toc)


distclean-local:
	(cd examples; make distclean)
	rm -rf standalone/bin

doc:
	$(GAP_EXEC) -A --quitonbreak -b -q < makedoc.g

.PHONY: doc

#test:
#	(cd examples; make)
