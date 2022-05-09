```
  duration_time                                      [Tool event]
  branch-instructions OR cpu/branch-instructions/    [Kernel PMU event]
  branch-misses OR cpu/branch-misses/                [Kernel PMU event]
  bus-cycles OR cpu/bus-cycles/                      [Kernel PMU event]
  cache-misses OR cpu/cache-misses/                  [Kernel PMU event]
  cache-references OR cpu/cache-references/          [Kernel PMU event]
  cpu-cycles OR cpu/cpu-cycles/                      [Kernel PMU event]
  cstate_core/c3-residency/                          [Kernel PMU event]
  cstate_core/c6-residency/                          [Kernel PMU event]
  cstate_core/c7-residency/                          [Kernel PMU event]
  cstate_pkg/c10-residency/                          [Kernel PMU event]
  cstate_pkg/c2-residency/                           [Kernel PMU event]
  cstate_pkg/c3-residency/                           [Kernel PMU event]
  cstate_pkg/c6-residency/                           [Kernel PMU event]
  cstate_pkg/c7-residency/                           [Kernel PMU event]
  cstate_pkg/c8-residency/                           [Kernel PMU event]
  cstate_pkg/c9-residency/                           [Kernel PMU event]
  cycles-ct OR cpu/cycles-ct/                        [Kernel PMU event]
  cycles-t OR cpu/cycles-t/                          [Kernel PMU event]
  el-abort OR cpu/el-abort/                          [Kernel PMU event]
  el-capacity OR cpu/el-capacity/                    [Kernel PMU event]
  el-commit OR cpu/el-commit/                        [Kernel PMU event]
  el-conflict OR cpu/el-conflict/                    [Kernel PMU event]
  el-start OR cpu/el-start/                          [Kernel PMU event]
  i915/actual-frequency/                             [Kernel PMU event]
  i915/bcs0-busy/                                    [Kernel PMU event]
  i915/bcs0-sema/                                    [Kernel PMU event]
  i915/bcs0-wait/                                    [Kernel PMU event]
  i915/interrupts/                                   [Kernel PMU event]
  i915/rc6-residency/                                [Kernel PMU event]
  i915/rcs0-busy/                                    [Kernel PMU event]
  i915/rcs0-sema/                                    [Kernel PMU event]
  i915/rcs0-wait/                                    [Kernel PMU event]
  i915/requested-frequency/                          [Kernel PMU event]
  i915/vcs0-busy/                                    [Kernel PMU event]
  i915/vcs0-sema/                                    [Kernel PMU event]
  i915/vcs0-wait/                                    [Kernel PMU event]
  i915/vecs0-busy/                                   [Kernel PMU event]
  i915/vecs0-sema/                                   [Kernel PMU event]
  i915/vecs0-wait/                                   [Kernel PMU event]
  instructions OR cpu/instructions/                  [Kernel PMU event]
  intel_pt//                                         [Kernel PMU event]
  mem-loads OR cpu/mem-loads/                        [Kernel PMU event]
  mem-stores OR cpu/mem-stores/                      [Kernel PMU event]
  msr/aperf/                                         [Kernel PMU event]
  msr/cpu_thermal_margin/                            [Kernel PMU event]
  msr/mperf/                                         [Kernel PMU event]
  msr/pperf/                                         [Kernel PMU event]
  msr/smi/                                           [Kernel PMU event]
  msr/tsc/                                           [Kernel PMU event]
  power/energy-cores/                                [Kernel PMU event]
  power/energy-gpu/                                  [Kernel PMU event]
  power/energy-pkg/                                  [Kernel PMU event]
  power/energy-ram/                                  [Kernel PMU event]
  ref-cycles OR cpu/ref-cycles/                      [Kernel PMU event]
  topdown-fetch-bubbles OR cpu/topdown-fetch-bubbles/ [Kernel PMU event]
  topdown-recovery-bubbles OR cpu/topdown-recovery-bubbles/ [Kernel PMU event]
  topdown-slots-issued OR cpu/topdown-slots-issued/  [Kernel PMU event]
  topdown-slots-retired OR cpu/topdown-slots-retired/ [Kernel PMU event]
  topdown-total-slots OR cpu/topdown-total-slots/    [Kernel PMU event]
  tx-abort OR cpu/tx-abort/                          [Kernel PMU event]
  tx-capacity OR cpu/tx-capacity/                    [Kernel PMU event]
  tx-commit OR cpu/tx-commit/                        [Kernel PMU event]
  tx-conflict OR cpu/tx-conflict/                    [Kernel PMU event]
  tx-start OR cpu/tx-start/                          [Kernel PMU event]
  uncore_cbox_0/clockticks/                          [Kernel PMU event]
  uncore_cbox_1/clockticks/                          [Kernel PMU event]
  uncore_cbox_2/clockticks/                          [Kernel PMU event]
  uncore_cbox_3/clockticks/                          [Kernel PMU event]
  uncore_imc/data_reads/                             [Kernel PMU event]
  uncore_imc/data_writes/                            [Kernel PMU event]

cache:
  l1d.replacement                                   
       [L1D data line replacements]
  l1d_pend_miss.fb_full                             
       [Number of times a request needed a FB entry but there was no entry
        available for it. That is the FB unavailability was dominant reason
        for blocking the request. A request includes cacheable/uncacheable
        demands that is load, store or SW prefetch]
  l1d_pend_miss.pending                             
       [L1D miss outstandings duration in cycles]
  l1d_pend_miss.pending_cycles                      
       [Cycles with L1D load Misses outstanding]
  l1d_pend_miss.pending_cycles_any                  
       [Cycles with L1D load Misses outstanding from any thread on physical
        core]
  l2_lines_in.all                                   
       [L2 cache lines filling L2]
  l2_lines_out.non_silent                           
       [Counts the number of lines that are evicted by L2 cache when triggered
        by an L2 cache fill. Those lines are in Modified state. Modified lines
        are written back to L3]
  l2_lines_out.silent                               
       [Counts the number of lines that are silently dropped by L2 cache when
        triggered by an L2 cache fill. These lines are typically in Shared or
        Exclusive state. A non-threaded event]
  l2_lines_out.useless_hwpf                         
       [Counts the number of lines that have been hardware prefetched but not
        used and now evicted by L2 cache]
  l2_lines_out.useless_pref                         
       [This event is deprecated. Refer to new event L2_LINES_OUT.USELESS_HWPF]
  l2_rqsts.all_code_rd                              
       [L2 code requests]
  l2_rqsts.all_demand_data_rd                       
       [Demand Data Read requests]
  l2_rqsts.all_demand_miss                          
       [Demand requests that miss L2 cache]
  l2_rqsts.all_demand_references                    
       [Demand requests to L2 cache]
  l2_rqsts.all_pf                                   
       [Requests from the L1/L2/L3 hardware prefetchers or Load software
        prefetches]
  l2_rqsts.all_rfo                                  
       [RFO requests to L2 cache]
  l2_rqsts.code_rd_hit                              
       [L2 cache hits when fetching instructions, code reads]
  l2_rqsts.code_rd_miss                             
       [L2 cache misses when fetching instructions]
  l2_rqsts.demand_data_rd_hit                       
       [Demand Data Read requests that hit L2 cache]
  l2_rqsts.demand_data_rd_miss                      
       [Demand Data Read miss L2, no rejects]
  l2_rqsts.miss                                     
       [All requests that miss L2 cache]
  l2_rqsts.pf_hit                                   
       [Requests from the L1/L2/L3 hardware prefetchers or Load software
        prefetches that hit L2 cache]
  l2_rqsts.pf_miss                                  
       [Requests from the L1/L2/L3 hardware prefetchers or Load software
        prefetches that miss L2 cache]
  l2_rqsts.references                               
       [All L2 requests]
  l2_rqsts.rfo_hit                                  
       [RFO requests that hit L2 cache]
  l2_rqsts.rfo_miss                                 
       [RFO requests that miss L2 cache]
  l2_trans.l2_wb                                    
       [L2 writebacks that access L2 cache]
  longest_lat_cache.miss                            
       [Core-originated cacheable demand requests missed L3 Spec update:
        SKL057]
  longest_lat_cache.reference                       
       [Core-originated cacheable demand requests that refer to L3 Spec
        update: SKL057]
  mem_inst_retired.all_loads                        
       [All retired load instructions. (Precise Event) Supports address when
        precise]
  mem_inst_retired.all_stores                       
       [All retired store instructions. (Precise Event) Supports address when
        precise]
  mem_inst_retired.lock_loads                       
       [Retired load instructions with locked access. (Precise Event) Supports
        address when precise]
  mem_inst_retired.split_loads                      
       [Retired load instructions that split across a cacheline boundary.
        (Precise Event) Supports address when precise]
  mem_inst_retired.split_stores                     
       [Retired store instructions that split across a cacheline boundary.
        (Precise Event) Supports address when precise]
  mem_inst_retired.stlb_miss_loads                  
       [Retired load instructions that miss the STLB. (Precise Event) Supports
        address when precise]
  mem_inst_retired.stlb_miss_stores                 
       [Retired store instructions that miss the STLB. (Precise Event)
        Supports address when precise]
  mem_load_l3_hit_retired.xsnp_hit                  
       [Retired load instructions which data sources were L3 and cross-core
        snoop hits in on-pkg core cache Supports address when precise (Precise
        event)]
  mem_load_l3_hit_retired.xsnp_hitm                 
       [Retired load instructions which data sources were HitM responses from
        shared L3 Supports address when precise (Precise event)]
  mem_load_l3_hit_retired.xsnp_miss                 
       [Retired load instructions which data sources were L3 hit and
        cross-core snoop missed in on-pkg core cache Supports address when
        precise (Precise event)]
  mem_load_l3_hit_retired.xsnp_none                 
       [Retired load instructions which data sources were hits in L3 without
        snoops required Supports address when precise (Precise event)]
  mem_load_misc_retired.uc                          
       [Retired instructions with at least 1 uncacheable load or lock Supports
        address when precise (Precise event)]
  mem_load_retired.fb_hit                           
       [Retired load instructions which data sources were load missed L1 but
        hit FB due to preceding miss to the same cache line with data not
        ready Supports address when precise (Precise event)]
  mem_load_retired.l1_hit                           
       [Retired load instructions with L1 cache hits as data sources Supports
        address when precise (Precise event)]
  mem_load_retired.l1_miss                          
       [Retired load instructions missed L1 cache as data sources Supports
        address when precise (Precise event)]
  mem_load_retired.l2_hit                           
       [Retired load instructions with L2 cache hits as data sources Supports
        address when precise (Precise event)]
  mem_load_retired.l2_miss                          
       [Retired load instructions missed L2 cache as data sources Supports
        address when precise (Precise event)]
  mem_load_retired.l3_hit                           
       [Retired load instructions with L3 cache hits as data sources Supports
        address when precise (Precise event)]
  mem_load_retired.l3_miss                          
       [Retired load instructions missed L3 cache as data sources Supports
        address when precise (Precise event)]
  offcore_requests.all_data_rd                      
       [Demand and prefetch data reads]
  offcore_requests.all_requests                     
       [Any memory transaction that reached the SQ]
  offcore_requests.demand_code_rd                   
       [Cacheable and noncachaeble code read requests]
  offcore_requests.demand_data_rd                   
       [Demand Data Read requests sent to uncore]
  offcore_requests.demand_rfo                       
       [Demand RFO requests including regular RFOs, locks, ItoM]
  offcore_requests_buffer.sq_full                   
       [Offcore requests buffer cannot take more entries for this thread core]
  offcore_requests_outstanding.all_data_rd          
       [Offcore outstanding cacheable Core Data Read transactions in
        SuperQueue (SQ), queue to uncore]
  offcore_requests_outstanding.cycles_with_data_rd  
       [Cycles when offcore outstanding cacheable Core Data Read transactions
        are present in SuperQueue (SQ), queue to uncore]
  offcore_requests_outstanding.cycles_with_demand_code_rd
       [Cycles with offcore outstanding Code Reads transactions in the
        SuperQueue (SQ), queue to uncore]
  offcore_requests_outstanding.cycles_with_demand_data_rd
       [Cycles when offcore outstanding Demand Data Read transactions are
        present in SuperQueue (SQ), queue to uncore]
  offcore_requests_outstanding.cycles_with_demand_rfo
       [Cycles with offcore outstanding demand rfo reads transactions in
        SuperQueue (SQ), queue to uncore]
  offcore_requests_outstanding.demand_code_rd       
       [Offcore outstanding Code Reads transactions in the SuperQueue (SQ),
        queue to uncore, every cycle]
  offcore_requests_outstanding.demand_data_rd       
       [Offcore outstanding Demand Data Read transactions in uncore queue]
  offcore_requests_outstanding.demand_data_rd_ge_6  
       [Cycles with at least 6 offcore outstanding Demand Data Read
        transactions in uncore queue]
  offcore_requests_outstanding.demand_rfo           
       [Offcore outstanding demand rfo reads transactions in SuperQueue (SQ),
        queue to uncore, every cycle]
  offcore_response                                  
       [Offcore response can be programmed only with a specific pair of event
        select and counter MSR, and with specific event codes and predefine
        mask bit value in a dedicated MSR to specify attributes of the offcore
        transaction]
  offcore_response.demand_code_rd.any_response      
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that have any response type]
  offcore_response.demand_code_rd.l3_hit.any_snoop  
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit.snoop_hit_no_fwd
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit.snoop_hitm 
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit.snoop_miss 
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit.snoop_none 
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit.snoop_not_needed
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit.spl_hit    
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_e.any_snoop
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_e.snoop_hit_no_fwd
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_e.snoop_hitm
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_e.snoop_miss
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_e.snoop_none
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_e.snoop_not_needed
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_e.spl_hit  
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_m.any_snoop
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_m.snoop_hit_no_fwd
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_m.snoop_hitm
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_m.snoop_miss
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_m.snoop_none
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_m.snoop_not_needed
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_m.spl_hit  
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_s.any_snoop
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_s.snoop_hit_no_fwd
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_s.snoop_hitm
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_s.snoop_miss
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_s.snoop_none
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_s.snoop_not_needed
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_s.spl_hit  
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l4_hit_local_l4.any_snoop
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l4_hit_local_l4.snoop_hit_no_fwd
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l4_hit_local_l4.snoop_hitm
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l4_hit_local_l4.snoop_miss
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l4_hit_local_l4.snoop_none
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l4_hit_local_l4.snoop_not_needed
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l4_hit_local_l4.spl_hit
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.supplier_none.any_snoop
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.supplier_none.snoop_hit_no_fwd
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.supplier_none.snoop_hitm
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.supplier_none.snoop_miss
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.supplier_none.snoop_none
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.supplier_none.snoop_not_needed
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.supplier_none.spl_hit
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_data_rd.any_response      
       [Counts demand data reads have any response type]
  offcore_response.demand_data_rd.l3_hit.any_snoop  
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit.snoop_hit_no_fwd
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit.snoop_hitm 
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit.snoop_miss 
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit.snoop_none 
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit.snoop_not_needed
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit.spl_hit    
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_e.any_snoop
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_e.snoop_hit_no_fwd
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_e.snoop_hitm
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_e.snoop_miss
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_e.snoop_none
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_e.snoop_not_needed
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_e.spl_hit  
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_m.any_snoop
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_m.snoop_hit_no_fwd
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_m.snoop_hitm
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_m.snoop_miss
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_m.snoop_none
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_m.snoop_not_needed
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_m.spl_hit  
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_s.any_snoop
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_s.snoop_hit_no_fwd
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_s.snoop_hitm
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_s.snoop_miss
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_s.snoop_none
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_s.snoop_not_needed
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_s.spl_hit  
       [Counts demand data reads]
  offcore_response.demand_data_rd.l4_hit_local_l4.any_snoop
       [Counts demand data reads]
  offcore_response.demand_data_rd.l4_hit_local_l4.snoop_hit_no_fwd
       [Counts demand data reads]
  offcore_response.demand_data_rd.l4_hit_local_l4.snoop_hitm
       [Counts demand data reads]
  offcore_response.demand_data_rd.l4_hit_local_l4.snoop_miss
       [Counts demand data reads]
  offcore_response.demand_data_rd.l4_hit_local_l4.snoop_none
       [Counts demand data reads]
  offcore_response.demand_data_rd.l4_hit_local_l4.snoop_not_needed
       [Counts demand data reads]
  offcore_response.demand_data_rd.l4_hit_local_l4.spl_hit
       [Counts demand data reads]
  offcore_response.demand_data_rd.supplier_none.any_snoop
       [Counts demand data reads]
  offcore_response.demand_data_rd.supplier_none.snoop_hit_no_fwd
       [Counts demand data reads]
  offcore_response.demand_data_rd.supplier_none.snoop_hitm
       [Counts demand data reads]
  offcore_response.demand_data_rd.supplier_none.snoop_miss
       [Counts demand data reads]
  offcore_response.demand_data_rd.supplier_none.snoop_none
       [Counts demand data reads]
  offcore_response.demand_data_rd.supplier_none.snoop_not_needed
       [Counts demand data reads]
  offcore_response.demand_data_rd.supplier_none.spl_hit
       [Counts demand data reads]
  offcore_response.demand_rfo.any_response          
       [Counts all demand data writes (RFOs) have any response type]
  offcore_response.demand_rfo.l3_hit.any_snoop      
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit.snoop_hit_no_fwd
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit.snoop_hitm     
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit.snoop_miss     
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit.snoop_none     
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit.snoop_not_needed
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit.spl_hit        
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_e.any_snoop    
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_e.snoop_hit_no_fwd
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_e.snoop_hitm   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_e.snoop_miss   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_e.snoop_none   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_e.snoop_not_needed
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_e.spl_hit      
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_m.any_snoop    
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_m.snoop_hit_no_fwd
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_m.snoop_hitm   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_m.snoop_miss   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_m.snoop_none   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_m.snoop_not_needed
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_m.spl_hit      
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_s.any_snoop    
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_s.snoop_hit_no_fwd
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_s.snoop_hitm   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_s.snoop_miss   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_s.snoop_none   
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_s.snoop_not_needed
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_s.spl_hit      
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l4_hit_local_l4.any_snoop
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l4_hit_local_l4.snoop_hit_no_fwd
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l4_hit_local_l4.snoop_hitm
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l4_hit_local_l4.snoop_miss
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l4_hit_local_l4.snoop_none
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l4_hit_local_l4.snoop_not_needed
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l4_hit_local_l4.spl_hit
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.supplier_none.any_snoop
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.supplier_none.snoop_hit_no_fwd
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.supplier_none.snoop_hitm
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.supplier_none.snoop_miss
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.supplier_none.snoop_none
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.supplier_none.snoop_not_needed
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.supplier_none.spl_hit 
       [Counts all demand data writes (RFOs)]
  offcore_response.other.any_response               
       [Counts any other requests have any response type]
  offcore_response.other.l3_hit.any_snoop           
       [Counts any other requests]
  offcore_response.other.l3_hit.snoop_hit_no_fwd    
       [Counts any other requests]
  offcore_response.other.l3_hit.snoop_hitm          
       [Counts any other requests]
  offcore_response.other.l3_hit.snoop_miss          
       [Counts any other requests]
  offcore_response.other.l3_hit.snoop_none          
       [Counts any other requests]
  offcore_response.other.l3_hit.snoop_not_needed    
       [Counts any other requests]
  offcore_response.other.l3_hit.spl_hit             
       [Counts any other requests]
  offcore_response.other.l3_hit_e.any_snoop         
       [Counts any other requests]
  offcore_response.other.l3_hit_e.snoop_hit_no_fwd  
       [Counts any other requests]
  offcore_response.other.l3_hit_e.snoop_hitm        
       [Counts any other requests]
  offcore_response.other.l3_hit_e.snoop_miss        
       [Counts any other requests]
  offcore_response.other.l3_hit_e.snoop_none        
       [Counts any other requests]
  offcore_response.other.l3_hit_e.snoop_not_needed  
       [Counts any other requests]
  offcore_response.other.l3_hit_e.spl_hit           
       [Counts any other requests]
  offcore_response.other.l3_hit_m.any_snoop         
       [Counts any other requests]
  offcore_response.other.l3_hit_m.snoop_hit_no_fwd  
       [Counts any other requests]
  offcore_response.other.l3_hit_m.snoop_hitm        
       [Counts any other requests]
  offcore_response.other.l3_hit_m.snoop_miss        
       [Counts any other requests]
  offcore_response.other.l3_hit_m.snoop_none        
       [Counts any other requests]
  offcore_response.other.l3_hit_m.snoop_not_needed  
       [Counts any other requests]
  offcore_response.other.l3_hit_m.spl_hit           
       [Counts any other requests]
  offcore_response.other.l3_hit_s.any_snoop         
       [Counts any other requests]
  offcore_response.other.l3_hit_s.snoop_hit_no_fwd  
       [Counts any other requests]
  offcore_response.other.l3_hit_s.snoop_hitm        
       [Counts any other requests]
  offcore_response.other.l3_hit_s.snoop_miss        
       [Counts any other requests]
  offcore_response.other.l3_hit_s.snoop_none        
       [Counts any other requests]
  offcore_response.other.l3_hit_s.snoop_not_needed  
       [Counts any other requests]
  offcore_response.other.l3_hit_s.spl_hit           
       [Counts any other requests]
  offcore_response.other.l4_hit_local_l4.any_snoop  
       [Counts any other requests]
  offcore_response.other.l4_hit_local_l4.snoop_hit_no_fwd
       [Counts any other requests]
  offcore_response.other.l4_hit_local_l4.snoop_hitm 
       [Counts any other requests]
  offcore_response.other.l4_hit_local_l4.snoop_miss 
       [Counts any other requests]
  offcore_response.other.l4_hit_local_l4.snoop_none 
       [Counts any other requests]
  offcore_response.other.l4_hit_local_l4.snoop_not_needed
       [Counts any other requests]
  offcore_response.other.l4_hit_local_l4.spl_hit    
       [Counts any other requests]
  offcore_response.other.supplier_none.any_snoop    
       [Counts any other requests]
  offcore_response.other.supplier_none.snoop_hit_no_fwd
       [Counts any other requests]
  offcore_response.other.supplier_none.snoop_hitm   
       [Counts any other requests]
  offcore_response.other.supplier_none.snoop_miss   
       [Counts any other requests]
  offcore_response.other.supplier_none.snoop_none   
       [Counts any other requests]
  offcore_response.other.supplier_none.snoop_not_needed
       [Counts any other requests]
  offcore_response.other.supplier_none.spl_hit      
       [Counts any other requests]
  sq_misc.split_lock                                
       [Number of cache line split locks sent to uncore]

floating point:
  fp_arith_inst_retired.128b_packed_double          
       [Number of SSE/AVX computational 128-bit packed double precision
        floating-point instructions retired. Each count represents 2
        computations. Applies to SSE* and AVX* packed double precision
        floating-point instructions: ADD SUB MUL DIV MIN MAX SQRT DPP
        FM(N)ADD/SUB. DPP and FM(N)ADD/SUB instructions count twice as they
        perform multiple calculations per element]
  fp_arith_inst_retired.128b_packed_single          
       [Number of SSE/AVX computational 128-bit packed single precision
        floating-point instructions retired. Each count represents 4
        computations. Applies to SSE* and AVX* packed single precision
        floating-point instructions: ADD SUB MUL DIV MIN MAX RCP RSQRT SQRT
        DPP FM(N)ADD/SUB. DPP and FM(N)ADD/SUB instructions count twice as
        they perform multiple calculations per element]
  fp_arith_inst_retired.256b_packed_double          
       [Number of SSE/AVX computational 256-bit packed double precision
        floating-point instructions retired. Each count represents 4
        computations. Applies to SSE* and AVX* packed double precision
        floating-point instructions: ADD SUB MUL DIV MIN MAX SQRT DPP
        FM(N)ADD/SUB. DPP and FM(N)ADD/SUB instructions count twice as they
        perform multiple calculations per element]
  fp_arith_inst_retired.256b_packed_single          
       [Number of SSE/AVX computational 256-bit packed single precision
        floating-point instructions retired. Each count represents 8
        computations. Applies to SSE* and AVX* packed single precision
        floating-point instructions: ADD SUB MUL DIV MIN MAX RCP RSQRT SQRT
        DPP FM(N)ADD/SUB. DPP and FM(N)ADD/SUB instructions count twice as
        they perform multiple calculations per element]
  fp_arith_inst_retired.scalar_double               
       [Number of SSE/AVX computational scalar double precision floating-point
        instructions retired. Each count represents 1 computation. Applies to
        SSE* and AVX* scalar double precision floating-point instructions: ADD
        SUB MUL DIV MIN MAX SQRT FM(N)ADD/SUB. FM(N)ADD/SUB instructions count
        twice as they perform multiple calculations per element]
  fp_arith_inst_retired.scalar_single               
       [Number of SSE/AVX computational scalar single precision floating-point
        instructions retired. Each count represents 1 computation. Applies to
        SSE* and AVX* scalar single precision floating-point instructions: ADD
        SUB MUL DIV MIN MAX RCP RSQRT SQRT FM(N)ADD/SUB. FM(N)ADD/SUB
        instructions count twice as they perform multiple calculations per
        element]
  fp_assist.any                                     
       [Cycles with any input/output SSE or FP assist]

frontend:
  dsb2mite_switches.penalty_cycles                  
       [Decode Stream Buffer (DSB)-to-MITE switch true penalty cycles]
  frontend_retired.dsb_miss                         
       [Retired Instructions who experienced decode stream buffer (DSB - the
        decoded instruction-cache) miss. Precise Event (Precise event)]
  frontend_retired.itlb_miss                        
       [Retired Instructions who experienced iTLB true miss. Precise Event
        (Precise event)]
  frontend_retired.l1i_miss                         
       [Retired Instructions who experienced Instruction L1 Cache true miss.
        Precise Event (Precise event)]
  frontend_retired.l2_miss                          
       [Retired Instructions who experienced Instruction L2 Cache true miss.
        Precise Event (Precise event)]
  frontend_retired.latency_ge_128                   
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 128 cycles which was not
        interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_16                    
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 16 cycles which was not
        interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_2                     
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 2 cycles which was not
        interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_256                   
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 256 cycles which was not
        interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_2_bubbles_ge_1        
       [Retired instructions that are fetched after an interval where the
        front-end had at least 1 bubble-slot for a period of 2 cycles which
        was not interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_2_bubbles_ge_2        
       [Retired instructions that are fetched after an interval where the
        front-end had at least 2 bubble-slots for a period of 2 cycles which
        was not interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_2_bubbles_ge_3        
       [Retired instructions that are fetched after an interval where the
        front-end had at least 3 bubble-slots for a period of 2 cycles which
        was not interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_32                    
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 32 cycles which was not
        interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_4                     
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 4 cycles which was not
        interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_512                   
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 512 cycles which was not
        interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_64                    
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 64 cycles which was not
        interrupted by a back-end stall. Precise Event (Precise event)]
  frontend_retired.latency_ge_8                     
       [Retired instructions that are fetched after an interval where the
        front-end delivered no uops for a period of 8 cycles which was not
        interrupted by a back-end stall (Precise event)]
  frontend_retired.stlb_miss                        
       [Retired Instructions who experienced STLB (2nd level TLB) true miss.
        Precise Event (Precise event)]
  icache_16b.ifdata_stall                           
       [Cycles where a code fetch is stalled due to L1 instruction cache miss]
  icache_64b.iftag_hit                              
       [Instruction fetch tag lookups that hit in the instruction cache (L1I).
        Counts at 64-byte cache-line granularity]
  icache_64b.iftag_miss                             
       [Instruction fetch tag lookups that miss in the instruction cache
        (L1I). Counts at 64-byte cache-line granularity]
  icache_64b.iftag_stall                            
       [Cycles where a code fetch is stalled due to L1 instruction cache tag
        miss]
  idq.all_dsb_cycles_4_uops                         
       [Cycles Decode Stream Buffer (DSB) is delivering 4 Uops]
  idq.all_dsb_cycles_any_uops                       
       [Cycles Decode Stream Buffer (DSB) is delivering any Uop]
  idq.all_mite_cycles_4_uops                        
       [Cycles MITE is delivering 4 Uops]
  idq.all_mite_cycles_any_uops                      
       [Cycles MITE is delivering any Uop]
  idq.dsb_cycles                                    
       [Cycles when uops are being delivered to Instruction Decode Queue (IDQ)
        from Decode Stream Buffer (DSB) path]
  idq.dsb_uops                                      
       [Uops delivered to Instruction Decode Queue (IDQ) from the Decode
        Stream Buffer (DSB) path]
  idq.mite_cycles                                   
       [Cycles when uops are being delivered to Instruction Decode Queue (IDQ)
        from MITE path]
  idq.mite_uops                                     
       [Uops delivered to Instruction Decode Queue (IDQ) from MITE path]
  idq.ms_cycles                                     
       [Cycles when uops are being delivered to Instruction Decode Queue (IDQ)
        while Microcode Sequenser (MS) is busy]
  idq.ms_dsb_cycles                                 
       [Cycles when uops initiated by Decode Stream Buffer (DSB) are being
        delivered to Instruction Decode Queue (IDQ) while Microcode Sequenser
        (MS) is busy]
  idq.ms_mite_uops                                  
       [Uops initiated by MITE and delivered to Instruction Decode Queue (IDQ)
        while Microcode Sequenser (MS) is busy]
  idq.ms_switches                                   
       [Number of switches from DSB (Decode Stream Buffer) or MITE (legacy
        decode pipeline) to the Microcode Sequencer]
  idq.ms_uops                                       
       [Uops delivered to Instruction Decode Queue (IDQ) while Microcode
        Sequenser (MS) is busy]
  idq_uops_not_delivered.core                       
       [Uops not delivered to Resource Allocation Table (RAT) per thread when
        backend of the machine is not stalled]
  idq_uops_not_delivered.cycles_0_uops_deliv.core   
       [Cycles per thread when 4 or more uops are not delivered to Resource
        Allocation Table (RAT) when backend of the machine is not stalled]
  idq_uops_not_delivered.cycles_fe_was_ok           
       [Counts cycles FE delivered 4 uops or Resource Allocation Table (RAT)
        was stalling FE]
  idq_uops_not_delivered.cycles_le_1_uop_deliv.core 
       [Cycles per thread when 3 or more uops are not delivered to Resource
        Allocation Table (RAT) when backend of the machine is not stalled]
  idq_uops_not_delivered.cycles_le_2_uop_deliv.core 
       [Cycles with less than 2 uops delivered by the front end]
  idq_uops_not_delivered.cycles_le_3_uop_deliv.core 
       [Cycles with less than 3 uops delivered by the front end]

memory:
  cycle_activity.cycles_l3_miss                     
       [Cycles while L3 cache miss demand load is outstanding]
  cycle_activity.stalls_l3_miss                     
       [Execution stalls while L3 cache miss demand load is outstanding]
  hle_retired.aborted                               
       [Number of times an HLE execution aborted due to any reasons (multiple
        categories may count as one) (Precise event)]
  hle_retired.aborted_events                        
       [Number of times an HLE execution aborted due to unfriendly events
        (such as interrupts)]
  hle_retired.aborted_mem                           
       [Number of times an HLE execution aborted due to various memory events
        (e.g., read/write capacity and conflicts)]
  hle_retired.aborted_memtype                       
       [Number of times an HLE execution aborted due to incompatible memory
        type]
  hle_retired.aborted_timer                         
       [Number of times an HLE execution aborted due to hardware timer
        expiration]
  hle_retired.aborted_unfriendly                    
       [Number of times an HLE execution aborted due to HLE-unfriendly
        instructions and certain unfriendly events (such as AD assists etc.)]
  hle_retired.commit                                
       [Number of times an HLE execution successfully committed]
  hle_retired.start                                 
       [Number of times an HLE execution started]
  machine_clears.memory_ordering                    
       [Counts the number of machine clears due to memory order conflicts Spec
        update: SKL089]
  mem_trans_retired.load_latency_gt_128             
       [Counts randomly selected loads when the latency from first dispatch to
        completion is greater than 128 cycles (Must be precise)]
  mem_trans_retired.load_latency_gt_16              
       [Counts randomly selected loads when the latency from first dispatch to
        completion is greater than 16 cycles (Must be precise)]
  mem_trans_retired.load_latency_gt_256             
       [Counts randomly selected loads when the latency from first dispatch to
        completion is greater than 256 cycles (Must be precise)]
  mem_trans_retired.load_latency_gt_32              
       [Counts randomly selected loads when the latency from first dispatch to
        completion is greater than 32 cycles (Must be precise)]
  mem_trans_retired.load_latency_gt_4               
       [Counts randomly selected loads when the latency from first dispatch to
        completion is greater than 4 cycles (Must be precise)]
  mem_trans_retired.load_latency_gt_512             
       [Counts randomly selected loads when the latency from first dispatch to
        completion is greater than 512 cycles (Must be precise)]
  mem_trans_retired.load_latency_gt_64              
       [Counts randomly selected loads when the latency from first dispatch to
        completion is greater than 64 cycles (Must be precise)]
  mem_trans_retired.load_latency_gt_8               
       [Counts randomly selected loads when the latency from first dispatch to
        completion is greater than 8 cycles (Must be precise)]
  offcore_requests.l3_miss_demand_data_rd           
       [Demand Data Read requests who miss L3 cache]
  offcore_requests_outstanding.cycles_with_l3_miss_demand_data_rd
       [Cycles with at least 1 Demand Data Read requests who miss L3 cache in
        the superQ]
  offcore_requests_outstanding.l3_miss_demand_data_rd
       [Counts number of Offcore outstanding Demand Data Read requests that
        miss L3 cache in the superQ every cycle]
  offcore_requests_outstanding.l3_miss_demand_data_rd_ge_6
       [Cycles with at least 6 Demand Data Read requests that miss L3 cache in
        the superQ]
  offcore_response.demand_code_rd.l3_hit.snoop_non_dram
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_e.snoop_non_dram
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_m.snoop_non_dram
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_hit_s.snoop_non_dram
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss.any_snoop 
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss.snoop_hit_no_fwd
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss.snoop_hitm
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss.snoop_miss
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss.snoop_non_dram
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss.snoop_none
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss.snoop_not_needed
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss.spl_hit   
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss_local_dram.any_snoop
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss_local_dram.snoop_hit_no_fwd
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss_local_dram.snoop_hitm
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss_local_dram.snoop_miss
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss_local_dram.snoop_non_dram
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss_local_dram.snoop_none
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss_local_dram.snoop_not_needed
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l3_miss_local_dram.spl_hit
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.l4_hit_local_l4.snoop_non_dram
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_code_rd.supplier_none.snoop_non_dram
       [Counts demand instruction fetches and L1 instruction cache prefetches
        that]
  offcore_response.demand_data_rd.l3_hit.snoop_non_dram
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_e.snoop_non_dram
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_m.snoop_non_dram
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_hit_s.snoop_non_dram
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss.any_snoop 
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss.snoop_hit_no_fwd
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss.snoop_hitm
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss.snoop_miss
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss.snoop_non_dram
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss.snoop_none
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss.snoop_not_needed
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss.spl_hit   
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss_local_dram.any_snoop
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss_local_dram.snoop_hit_no_fwd
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss_local_dram.snoop_hitm
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss_local_dram.snoop_miss
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss_local_dram.snoop_non_dram
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss_local_dram.snoop_none
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss_local_dram.snoop_not_needed
       [Counts demand data reads]
  offcore_response.demand_data_rd.l3_miss_local_dram.spl_hit
       [Counts demand data reads]
  offcore_response.demand_data_rd.l4_hit_local_l4.snoop_non_dram
       [Counts demand data reads]
  offcore_response.demand_data_rd.supplier_none.snoop_non_dram
       [Counts demand data reads]
  offcore_response.demand_rfo.l3_hit.snoop_non_dram 
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_e.snoop_non_dram
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_m.snoop_non_dram
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_hit_s.snoop_non_dram
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss.any_snoop     
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss.snoop_hit_no_fwd
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss.snoop_hitm    
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss.snoop_miss    
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss.snoop_non_dram
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss.snoop_none    
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss.snoop_not_needed
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss.spl_hit       
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss_local_dram.any_snoop
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss_local_dram.snoop_hit_no_fwd
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss_local_dram.snoop_hitm
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss_local_dram.snoop_miss
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss_local_dram.snoop_non_dram
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss_local_dram.snoop_none
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss_local_dram.snoop_not_needed
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l3_miss_local_dram.spl_hit
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.l4_hit_local_l4.snoop_non_dram
       [Counts all demand data writes (RFOs)]
  offcore_response.demand_rfo.supplier_none.snoop_non_dram
       [Counts all demand data writes (RFOs)]
  offcore_response.other.l3_hit.snoop_non_dram      
       [Counts any other requests]
  offcore_response.other.l3_hit_e.snoop_non_dram    
       [Counts any other requests]
  offcore_response.other.l3_hit_m.snoop_non_dram    
       [Counts any other requests]
  offcore_response.other.l3_hit_s.snoop_non_dram    
       [Counts any other requests]
  offcore_response.other.l3_miss.any_snoop          
       [Counts any other requests]
  offcore_response.other.l3_miss.snoop_hit_no_fwd   
       [Counts any other requests]
  offcore_response.other.l3_miss.snoop_hitm         
       [Counts any other requests]
  offcore_response.other.l3_miss.snoop_miss         
       [Counts any other requests]
  offcore_response.other.l3_miss.snoop_non_dram     
       [Counts any other requests]
  offcore_response.other.l3_miss.snoop_none         
       [Counts any other requests]
  offcore_response.other.l3_miss.snoop_not_needed   
       [Counts any other requests]
  offcore_response.other.l3_miss.spl_hit            
       [Counts any other requests]
  offcore_response.other.l3_miss_local_dram.any_snoop
       [Counts any other requests]
  offcore_response.other.l3_miss_local_dram.snoop_hit_no_fwd
       [Counts any other requests]
  offcore_response.other.l3_miss_local_dram.snoop_hitm
       [Counts any other requests]
  offcore_response.other.l3_miss_local_dram.snoop_miss
       [Counts any other requests]
  offcore_response.other.l3_miss_local_dram.snoop_non_dram
       [Counts any other requests]
  offcore_response.other.l3_miss_local_dram.snoop_none
       [Counts any other requests]
  offcore_response.other.l3_miss_local_dram.snoop_not_needed
       [Counts any other requests]
  offcore_response.other.l3_miss_local_dram.spl_hit 
       [Counts any other requests]
  offcore_response.other.l4_hit_local_l4.snoop_non_dram
       [Counts any other requests]
  offcore_response.other.supplier_none.snoop_non_dram
       [Counts any other requests]
  rtm_retired.aborted                               
       [Number of times an RTM execution aborted due to any reasons (multiple
        categories may count as one) (Precise event)]
  rtm_retired.aborted_events                        
       [Number of times an RTM execution aborted due to none of the previous 4
        categories (e.g. interrupt)]
  rtm_retired.aborted_mem                           
       [Number of times an RTM execution aborted due to various memory events
        (e.g. read/write capacity and conflicts)]
  rtm_retired.aborted_memtype                       
       [Number of times an RTM execution aborted due to incompatible memory
        type]
  rtm_retired.aborted_timer                         
       [Number of times an RTM execution aborted due to uncommon conditions]
  rtm_retired.aborted_unfriendly                    
       [Number of times an RTM execution aborted due to HLE-unfriendly
        instructions]
  rtm_retired.commit                                
       [Number of times an RTM execution successfully committed]
  rtm_retired.start                                 
       [Number of times an RTM execution started]
  tx_exec.misc1                                     
       [Counts the number of times a class of instructions that may cause a
        transactional abort was executed. Since this is the count of
        execution, it may not always cause a transactional abort]
  tx_exec.misc2                                     
       [Counts the number of times a class of instructions (e.g., vzeroupper)
        that may cause a transactional abort was executed inside a
        transactional region]
  tx_exec.misc3                                     
       [Counts the number of times an instruction execution caused the
        transactional nest count supported to be exceeded]
  tx_exec.misc4                                     
       [Counts the number of times a XBEGIN instruction was executed inside an
        HLE transactional region]
  tx_exec.misc5                                     
       [Counts the number of times an HLE XACQUIRE instruction was executed
        inside an RTM transactional region]
  tx_mem.abort_capacity                             
       [Number of times a transactional abort was signaled due to a data
        capacity limitation for transactional reads or writes]
  tx_mem.abort_conflict                             
       [Number of times a transactional abort was signaled due to a data
        conflict on a transactionally accessed address]
  tx_mem.abort_hle_elision_buffer_mismatch          
       [Number of times an HLE transactional execution aborted due to XRELEASE
        lock not satisfying the address and value requirements in the elision
        buffer]
  tx_mem.abort_hle_elision_buffer_not_empty         
       [Number of times an HLE transactional execution aborted due to
        NoAllocatedElisionBuffer being non-zero]
  tx_mem.abort_hle_elision_buffer_unsupported_alignment
       [Number of times an HLE transactional execution aborted due to an
        unsupported read alignment from the elision buffer]
  tx_mem.abort_hle_store_to_elided_lock             
       [Number of times a HLE transactional region aborted due to a non
        XRELEASE prefixed instruction writing to an elided lock in the elision
        buffer]
  tx_mem.hle_elision_buffer_full                    
       [Number of times HLE lock could not be elided due to
        ElisionBufferAvailable being zero]

other:
  hw_interrupts.received                            
       [Number of hardware interrupts received by the processor]
  sw_prefetch_access.nta                            
       [Number of PREFETCHNTA instructions executed]
  sw_prefetch_access.prefetchw                      
       [Number of PREFETCHW instructions executed]
  sw_prefetch_access.t0                             
       [Number of PREFETCHT0 instructions executed]
  sw_prefetch_access.t1_t2                          
       [Number of PREFETCHT1 or PREFETCHT2 instructions executed]

pipeline:
  arith.divider_active                              
       [Cycles when divide unit is busy executing divide or square root
        operations. Accounts for integer and floating-point operations]
  baclears.any                                      
       [Counts the total number when the front end is resteered, mainly when
        the BPU cannot provide a correct prediction and this is corrected by
        other branch handling mechanisms at the front end]
  br_inst_retired.all_branches                      
       [All (macro) branch instructions retired Spec update: SKL091]
  br_inst_retired.all_branches_pebs                 
       [All (macro) branch instructions retired Spec update: SKL091 (Must be
        precise)]
  br_inst_retired.conditional                       
       [Conditional branch instructions retired Spec update: SKL091 (Precise
        event)]
  br_inst_retired.far_branch                        
       [Counts the number of far branch instructions retired Spec update:
        SKL091 (Precise event)]
  br_inst_retired.near_call                         
       [Direct and indirect near call instructions retired Spec update: SKL091
        (Precise event)]
  br_inst_retired.near_return                       
       [Return instructions retired Spec update: SKL091 (Precise event)]
  br_inst_retired.near_taken                        
       [Taken branch instructions retired Spec update: SKL091 (Precise event)]
  br_inst_retired.not_taken                         
       [Counts all not taken macro branch instructions retired Spec update:
        SKL091 (Precise event)]
  br_misp_retired.all_branches                      
       [All mispredicted macro branch instructions retired]
  br_misp_retired.all_branches_pebs                 
       [Mispredicted macro branch instructions retired (Must be precise)]
  br_misp_retired.conditional                       
       [Mispredicted conditional branch instructions retired (Precise event)]
  br_misp_retired.near_call                         
       [Mispredicted direct and indirect near call instructions retired
        (Precise event)]
  br_misp_retired.near_taken                        
       [Number of near branch instructions retired that were mispredicted and
        taken (Precise event)]
  cpu_clk_thread_unhalted.one_thread_active         
       [Core crystal clock cycles when this thread is unhalted and the other
        thread is halted]
  cpu_clk_thread_unhalted.ref_xclk                  
       [Core crystal clock cycles when the thread is unhalted]
  cpu_clk_thread_unhalted.ref_xclk_any              
       [Core crystal clock cycles when at least one thread on the physical
        core is unhalted]
  cpu_clk_unhalted.one_thread_active                
       [Core crystal clock cycles when this thread is unhalted and the other
        thread is halted]
  cpu_clk_unhalted.ref_tsc                          
       [Reference cycles when the core is not in halt state]
  cpu_clk_unhalted.ref_xclk                         
       [Core crystal clock cycles when the thread is unhalted]
  cpu_clk_unhalted.ref_xclk_any                     
       [Core crystal clock cycles when at least one thread on the physical
        core is unhalted]
  cpu_clk_unhalted.ring0_trans                      
       [Counts when there is a transition from ring 1, 2 or 3 to ring 0]
  cpu_clk_unhalted.thread                           
       [Core cycles when the thread is not in halt state]
  cpu_clk_unhalted.thread_any                       
       [Core cycles when at least one thread on the physical core is not in
        halt state]
  cpu_clk_unhalted.thread_p                         
       [Thread cycles when thread is not in halt state]
  cpu_clk_unhalted.thread_p_any                     
       [Core cycles when at least one thread on the physical core is not in
        halt state]
  cycle_activity.cycles_l1d_miss                    
       [Cycles while L1 cache miss demand load is outstanding]
  cycle_activity.cycles_l2_miss                     
       [Cycles while L2 cache miss demand load is outstanding]
  cycle_activity.cycles_mem_any                     
       [Cycles while memory subsystem has an outstanding load]
  cycle_activity.stalls_l1d_miss                    
       [Execution stalls while L1 cache miss demand load is outstanding]
  cycle_activity.stalls_l2_miss                     
       [Execution stalls while L2 cache miss demand load is outstanding]
  cycle_activity.stalls_mem_any                     
       [Execution stalls while memory subsystem has an outstanding load]
  cycle_activity.stalls_total                       
       [Total execution stalls]
  exe_activity.1_ports_util                         
       [Cycles total of 1 uop is executed on all ports and Reservation Station
        was not empty]
  exe_activity.2_ports_util                         
       [Cycles total of 2 uops are executed on all ports and Reservation
        Station was not empty]
  exe_activity.3_ports_util                         
       [Cycles total of 3 uops are executed on all ports and Reservation
        Station was not empty]
  exe_activity.4_ports_util                         
       [Cycles total of 4 uops are executed on all ports and Reservation
        Station was not empty]
  exe_activity.bound_on_stores                      
       [Cycles where the Store Buffer was full and no outstanding load]
  exe_activity.exe_bound_0_ports                    
       [Cycles where no uops were executed, the Reservation Station was not
        empty, the Store Buffer was full and there was no outstanding load]
  ild_stall.lcp                                     
       [Stalls caused by changing prefix length of the instruction]
  inst_retired.any                                  
       [Instructions retired from execution]
  inst_retired.any_p                                
       [Number of instructions retired. General Counter - architectural event
        Spec update: SKL091, SKL044]
  inst_retired.prec_dist                            
       [Precise instruction retired event with HW to reduce effect of PEBS
        shadow in IP distribution Spec update: SKL091, SKL044 (Must be
        precise)]
  inst_retired.total_cycles_ps                      
       [Number of cycles using always true condition applied to PEBS
        instructions retired event Spec update: SKL091, SKL044 (Must be
        precise)]
  int_misc.clear_resteer_cycles                     
       [Cycles the issue-stage is waiting for front-end to fetch from
        resteered path following branch misprediction or machine clear events]
  int_misc.recovery_cycles                          
       [Core cycles the allocator was stalled due to recovery from earlier
        clear event for this thread (e.g. misprediction or memory nuke)]
  int_misc.recovery_cycles_any                      
       [Core cycles the allocator was stalled due to recovery from earlier
        clear event for any thread running on the physical core (e.g.
        misprediction or memory nuke)]
  ld_blocks.no_sr                                   
       [The number of times that split load operations are temporarily blocked
        because all resources for handling the split accesses are in use]
  ld_blocks.store_forward                           
       [Loads blocked by overlapping with store buffer that cannot be
        forwarded]
  ld_blocks_partial.address_alias                   
       [False dependencies in MOB due to partial compare on address]
  load_hit_pre.sw_pf                                
       [Demand load dispatches that hit L1D fill buffer (FB) allocated for
        software prefetch]
  lsd.cycles_4_uops                                 
       [Cycles 4 Uops delivered by the LSD, but didn't come from the decoder]
  lsd.cycles_active                                 
       [Cycles Uops delivered by the LSD, but didn't come from the decoder]
  lsd.uops                                          
       [Number of Uops delivered by the LSD]
  machine_clears.count                              
       [Number of machine clears (nukes) of any type]
  machine_clears.smc                                
       [Self-modifying code (SMC) detected]
  other_assists.any                                 
       [Number of times a microcode assist is invoked by HW other than
        FP-assist. Examples include AD (page Access Dirty) and AVX* related
        assists]
  partial_rat_stalls.scoreboard                     
       [Cycles where the pipeline is stalled due to serializing operations]
  resource_stalls.any                               
       [Resource-related stall cycles]
  resource_stalls.sb                                
       [Cycles stalled due to no store buffers available. (not including
        draining form sync)]
  rob_misc_events.lbr_inserts                       
       [Increments whenever there is an update to the LBR array]
  rob_misc_events.pause_inst                        
       [Number of retired PAUSE instructions (that do not end up with a VMExit
        to the VMM; TSX aborted Instructions may be counted). This event is
        not supported on first SKL and KBL products]
  rs_events.empty_cycles                            
       [Cycles when Reservation Station (RS) is empty for the thread]
  rs_events.empty_end                               
       [Counts end of periods where the Reservation Station (RS) was empty.
        Could be useful to precisely locate Frontend Latency Bound issues]
  uops_dispatched_port.port_0                       
       [Cycles per thread when uops are executed in port 0]
  uops_dispatched_port.port_1                       
       [Cycles per thread when uops are executed in port 1]
  uops_dispatched_port.port_2                       
       [Cycles per thread when uops are executed in port 2]
  uops_dispatched_port.port_3                       
       [Cycles per thread when uops are executed in port 3]
  uops_dispatched_port.port_4                       
       [Cycles per thread when uops are executed in port 4]
  uops_dispatched_port.port_5                       
       [Cycles per thread when uops are executed in port 5]
  uops_dispatched_port.port_6                       
       [Cycles per thread when uops are executed in port 6]
  uops_dispatched_port.port_7                       
       [Cycles per thread when uops are executed in port 7]
  uops_executed.core                                
       [Number of uops executed on the core]
  uops_executed.core_cycles_ge_1                    
       [Cycles at least 1 micro-op is executed from any thread on physical
        core]
  uops_executed.core_cycles_ge_2                    
       [Cycles at least 2 micro-op is executed from any thread on physical
        core]
  uops_executed.core_cycles_ge_3                    
       [Cycles at least 3 micro-op is executed from any thread on physical
        core]
  uops_executed.core_cycles_ge_4                    
       [Cycles at least 4 micro-op is executed from any thread on physical
        core]
  uops_executed.core_cycles_none                    
       [Cycles with no micro-ops executed from any thread on physical core]
  uops_executed.cycles_ge_1_uop_exec                
       [Cycles where at least 1 uop was executed per-thread]
  uops_executed.cycles_ge_2_uops_exec               
       [Cycles where at least 2 uops were executed per-thread]
  uops_executed.cycles_ge_3_uops_exec               
       [Cycles where at least 3 uops were executed per-thread]
  uops_executed.cycles_ge_4_uops_exec               
       [Cycles where at least 4 uops were executed per-thread]
  uops_executed.stall_cycles                        
       [Counts number of cycles no uops were dispatched to be executed on this
        thread]
  uops_executed.thread                              
       [Counts the number of uops to be executed per-thread each cycle]
  uops_executed.x87                                 
       [Counts the number of x87 uops dispatched]
  uops_issued.any                                   
       [Uops that Resource Allocation Table (RAT) issues to Reservation
        Station (RS)]
  uops_issued.slow_lea                              
       [Number of slow LEA uops being allocated. A uop is generally considered
        SlowLea if it has 3 sources (e.g. 2 sources + immediate) regardless if
        as a result of LEA instruction or not]
  uops_issued.stall_cycles                          
       [Cycles when Resource Allocation Table (RAT) does not issue Uops to
        Reservation Station (RS) for the thread]
  uops_issued.vector_width_mismatch                 
       [Uops inserted at issue-stage in order to preserve upper bits of vector
        registers]
  uops_retired.retire_slots                         
       [Retirement slots used]
  uops_retired.stall_cycles                         
       [Cycles without actually retired uops]
  uops_retired.total_cycles                         
       [Cycles with less than 10 actually retired uops]

uncore:
  unc_arb_coh_trk_requests.all                      
       [Unit: uncore_arb Number of entries allocated. Account for Any type:
        e.g. Snoop, Core aperture, etc]
  unc_arb_trk_occupancy.all                         
       [Unit: uncore_arb Each cycle count number of all Core outgoing valid
        entries. Such entry is defined as valid from its allocation till first
        of IDI0 or DRS0 messages is sent out. Accounts for Coherent and
        non-coherent traffic]
  unc_arb_trk_occupancy.cycles_with_any_request     
       [Unit: uncore_arb Cycles with at least one request outstanding is
        waiting for data return from memory controller. Account for coherent
        and non-coherent requests initiated by IA Cores, Processor Graphics
        Unit, or LLC.;]
  unc_arb_trk_requests.all                          
       [Unit: uncore_arb Total number of Core outgoing entries allocated.
        Accounts for Coherent and non-coherent traffic]
  unc_arb_trk_requests.drd_direct                   
       [Unit: uncore_arb Number of Core coherent Data Read entries allocated
        in DirectData mode]
  unc_arb_trk_requests.writes                       
       [Unit: uncore_arb Number of Writes allocated - any write transactions:
        full/partials writes and evictions]
  unc_cbo_cache_lookup.any_es                       
       [Unit: uncore_cbox L3 Lookup any request that access cache and found
        line in E or S-state]
  unc_cbo_cache_lookup.any_i                        
       [Unit: uncore_cbox L3 Lookup any request that access cache and found
        line in I-state]
  unc_cbo_cache_lookup.any_m                        
       [Unit: uncore_cbox L3 Lookup any request that access cache and found
        line in M-state]
  unc_cbo_cache_lookup.any_mesi                     
       [Unit: uncore_cbox L3 Lookup any request that access cache and found
        line in MESI-state]
  unc_cbo_cache_lookup.read_es                      
       [Unit: uncore_cbox L3 Lookup read request that access cache and found
        line in E or S-state]
  unc_cbo_cache_lookup.read_i                       
       [Unit: uncore_cbox L3 Lookup read request that access cache and found
        line in I-state]
  unc_cbo_cache_lookup.read_mesi                    
       [Unit: uncore_cbox L3 Lookup read request that access cache and found
        line in any MESI-state]
  unc_cbo_cache_lookup.write_es                     
       [Unit: uncore_cbox L3 Lookup write request that access cache and found
        line in E or S-state]
  unc_cbo_cache_lookup.write_m                      
       [Unit: uncore_cbox L3 Lookup write request that access cache and found
        line in M-state]
  unc_cbo_cache_lookup.write_mesi                   
       [Unit: uncore_cbox L3 Lookup write request that access cache and found
        line in MESI-state]
  unc_cbo_xsnp_response.hit_xcore                   
       [Unit: uncore_cbox A cross-core snoop initiated by this Cbox due to
        processor core memory request which hits a non-modified line in some
        processor core]
  unc_cbo_xsnp_response.hitm_xcore                  
       [Unit: uncore_cbox A cross-core snoop initiated by this Cbox due to
        processor core memory request which hits a modified line in some
        processor core]
  unc_cbo_xsnp_response.miss_eviction               
       [Unit: uncore_cbox A cross-core snoop resulted from L3 Eviction which
        misses in some processor core]
  unc_cbo_xsnp_response.miss_xcore                  
       [Unit: uncore_cbox A cross-core snoop initiated by this Cbox due to
        processor core memory request which misses in some processor core]

virtual memory:
  dtlb_load_misses.miss_causes_a_walk               
       [Load misses in all DTLB levels that cause page walks]
  dtlb_load_misses.stlb_hit                         
       [Loads that miss the DTLB and hit the STLB]
  dtlb_load_misses.walk_active                      
       [Cycles when at least one PMH is busy with a page walk for a load. EPT
        page walk duration are excluded in Skylake]
  dtlb_load_misses.walk_completed                   
       [Load miss in all TLB levels causes a page walk that completes. (All
        page sizes)]
  dtlb_load_misses.walk_completed_1g                
       [Page walk completed due to a demand data load to a 1G page]
  dtlb_load_misses.walk_completed_2m_4m             
       [Page walk completed due to a demand data load to a 2M/4M page]
  dtlb_load_misses.walk_completed_4k                
       [Page walk completed due to a demand data load to a 4K page]
  dtlb_load_misses.walk_pending                     
       [Counts 1 per cycle for each PMH that is busy with a page walk for a
        load. EPT page walk duration are excluded in Skylake]
  dtlb_store_misses.miss_causes_a_walk              
       [Store misses in all DTLB levels that cause page walks]
  dtlb_store_misses.stlb_hit                        
       [Stores that miss the DTLB and hit the STLB]
  dtlb_store_misses.walk_active                     
       [Cycles when at least one PMH is busy with a page walk for a store. EPT
        page walk duration are excluded in Skylake]
  dtlb_store_misses.walk_completed                  
       [Store misses in all TLB levels causes a page walk that completes. (All
        page sizes)]
  dtlb_store_misses.walk_completed_1g               
       [Page walk completed due to a demand data store to a 1G page]
  dtlb_store_misses.walk_completed_2m_4m            
       [Page walk completed due to a demand data store to a 2M/4M page]
  dtlb_store_misses.walk_completed_4k               
       [Page walk completed due to a demand data store to a 4K page]
  dtlb_store_misses.walk_pending                    
       [Counts 1 per cycle for each PMH that is busy with a page walk for a
        store. EPT page walk duration are excluded in Skylake]
  ept.walk_pending                                  
       [Counts 1 per cycle for each PMH that is busy with a EPT (Extended Page
        Table) walk for any request type]
  itlb.itlb_flush                                   
       [Flushing of the Instruction TLB (ITLB) pages, includes 4k/2M/4M pages]
  itlb_misses.miss_causes_a_walk                    
       [Misses at all ITLB levels that cause page walks]
  itlb_misses.stlb_hit                              
       [Instruction fetch requests that miss the ITLB and hit the STLB]
  itlb_misses.walk_active                           
       [Cycles when at least one PMH is busy with a page walk for code
        (instruction fetch) request. EPT page walk duration are excluded in
        Skylake]
  itlb_misses.walk_completed                        
       [Code miss in all TLB levels causes a page walk that completes. (All
        page sizes)]
  itlb_misses.walk_completed_1g                     
       [Code miss in all TLB levels causes a page walk that completes. (1G)]
  itlb_misses.walk_completed_2m_4m                  
       [Code miss in all TLB levels causes a page walk that completes. (2M/4M)]
  itlb_misses.walk_completed_4k                     
       [Code miss in all TLB levels causes a page walk that completes. (4K)]
  itlb_misses.walk_pending                          
       [Counts 1 per cycle for each PMH that is busy with a page walk for an
        instruction fetch request. EPT page walk duration are excluded in
        Skylake]
  tlb_flush.dtlb_thread                             
       [DTLB flush attempts of the thread-specific entries]
  tlb_flush.stlb_any                                
       [STLB flush attempts]
  rNNN                                               [Raw hardware event descriptor]
  cpu/t1=v1[,t2=v2,t3 ...]/modifier                  [Raw hardware event descriptor]
  mem:<addr>[/len][:access]                          [Hardware breakpoint]

Metric Groups:

Branch_Mispredicts:
  Branch_Misprediction_Cost
       [Branch Misprediction Cost: Fraction of TopDown slots wasted per branch misprediction (jeclear and baclear)]
  IpMispredict
       [Number of Instructions per non-speculative Branch Misprediction (JEClear)]
Branch_Mispredicts_SMT:
  Branch_Misprediction_Cost_SMT
       [Branch Misprediction Cost: Fraction of TopDown slots wasted per branch misprediction (jeclear and baclear)]
Branches:
  BpTB
       [Branch instructions per taken branch]
  IpB
       [Instructions per Branch]
  IpCall
       [Instruction per (near) call]
  IpTB
       [Instruction per taken branch]
Cache_Misses:
  L1MPKI
       [L1 cache true misses per kilo instruction for retired demand loads]
  L2HPKI_All
       [L2 cache hits per kilo instruction for all request types (including speculative)]
  L2MPKI
       [L2 cache true misses per kilo instruction for retired demand loads]
  L2MPKI_All
       [L2 cache misses per kilo instruction for all request types (including speculative)]
  L3MPKI
       [L3 cache true misses per kilo instruction for retired demand loads]
DSB:
  DSB_Coverage
       [Fraction of Uops delivered by the DSB (aka Decoded ICache; or Uop Cache)]
FLOPS:
  FLOPc
       [Floating Point Operations Per Cycle]
  GFLOPs
       [Giga Floating Point Operations Per Second]
FLOPS_SMT:
  FLOPc_SMT
       [Floating Point Operations Per Cycle]
Frontend_Bandwidth:
  DSB_Coverage
       [Fraction of Uops delivered by the DSB (aka Decoded ICache; or Uop Cache)]
Instruction_Type:
  IpB
       [Instructions per Branch]
  IpL
       [Instructions per Load (lower number means loads are more frequent)]
  IpS
       [Instructions per Store]
L1_Bound:
  IpL
       [Instructions per Load (lower number means loads are more frequent)]
Memory_BW:
  DRAM_BW_Use
       [Average external Memory Bandwidth Use for reads and writes [GB / sec]]
  DRAM_Parallel_Reads
       [Average number of parallel data read requests to external memory. Accounts for demand loads and L1/L2 prefetches]
  L1D_Cache_Fill_BW
       [Average data fill bandwidth to the L1 data cache [GB / sec]]
  L2_Cache_Fill_BW
       [Average data fill bandwidth to the L2 cache [GB / sec]]
  L3_Cache_Access_BW
       [Average per-core data fill bandwidth to the L3 cache [GB / sec]]
  L3_Cache_Fill_BW
       [Average per-core data fill bandwidth to the L3 cache [GB / sec]]
  MLP
       [Memory-Level-Parallelism (average number of L1 miss demand load when there is at least one such miss. Per-thread)]
Memory_Bound:
  Load_Miss_Real_Latency
       [Actual Average Latency for L1 data-cache miss demand loads (in core cycles)]
  MLP
       [Memory-Level-Parallelism (average number of L1 miss demand load when there is at least one such miss. Per-thread)]
Memory_Lat:
  Load_Miss_Real_Latency
       [Actual Average Latency for L1 data-cache miss demand loads (in core cycles)]
No_group:
  L1MPKI
       [L1 cache true misses per kilo instruction for retired demand loads]
  L2HPKI_All
       [L2 cache hits per kilo instruction for all request types (including speculative)]
  L2MPKI
       [L2 cache true misses per kilo instruction for retired demand loads]
  L2MPKI_All
       [L2 cache misses per kilo instruction for all request types (including speculative)]
  L3MPKI
       [L3 cache true misses per kilo instruction for retired demand loads]
PGO:
  BpTB
       [Branch instructions per taken branch]
  IFetch_Line_Utilization
       [Rough Estimation of fraction of fetched lines bytes that were likely (includes speculatively fetches) consumed by program instructions]
  IpTB
       [Instruction per taken branch]
Pipeline:
  CPI
       [Cycles Per Instruction (threaded)]
  ILP
       [Instruction-Level-Parallelism (average number of uops executed when there is at least 1 uop executed)]
  UPI
       [Uops Per Instruction]
Port_5:
  IpB
       [Instructions per Branch]
Port_6:
  IpB
       [Instructions per Branch]
Ports_Utilization:
  ILP
       [Instruction-Level-Parallelism (average number of uops executed when there is at least 1 uop executed)]
Power:
  C2_Pkg_Residency
       [C2 residency percent per package]
  C3_Core_Residency
       [C3 residency percent per core]
  C3_Pkg_Residency
       [C3 residency percent per package]
  C6_Core_Residency
       [C6 residency percent per core]
  C6_Pkg_Residency
       [C6 residency percent per package]
  C7_Core_Residency
       [C7 residency percent per core]
  C7_Pkg_Residency
       [C7 residency percent per package]
  Turbo_Utilization
       [Average Frequency Utilization relative nominal frequency]
Retiring:
  UPI
       [Uops Per Instruction]
SMT:
  CORE_CLKS
       [Core actual clocks when any thread is active on the physical core]
  CoreIPC
       [Instructions Per Cycle (per physical core)]
  CoreIPC_SMT
       [Instructions Per Cycle (per physical core)]
  SMT_2T_Utilization
       [Fraction of cycles where both hardware threads were active]
Store_Bound:
  IpS
       [Instructions per Store]
Summary:
  CLKS
       [Per-thread actual clocks when the logical processor is active]
  CPI
       [Cycles Per Instruction (threaded)]
  CPU_Utilization
       [Average CPU Utilization]
  GFLOPs
       [Giga Floating Point Operations Per Second]
  Instructions
       [Total number of retired Instructions]
  Kernel_Utilization
       [Fraction of cycles spent in Kernel mode]
  SMT_2T_Utilization
       [Fraction of cycles where both hardware threads were active]
TLB:
  Page_Walks_Utilization
       [Utilization of the core's Page Walker(s) serving STLB misses triggered by instruction/Load/Store accesses]
TLB_SMT:
  Page_Walks_Utilization_SMT
       [Utilization of the core's Page Walker(s) serving STLB misses triggered by instruction/Load/Store accesses]
TopDownL1:
  IPC
       [Instructions Per Cycle (per logical thread)]
  SLOTS
       [Total issue-pipeline slots (per core)]
TopDownL1_SMT:
  SLOTS_SMT
       [Total issue-pipeline slots (per core)]
TopdownL1:
  Backend_Bound
       [This category represents fraction of slots where no uops are being delivered due to a lack of required resources for accepting new uops in the Backend]
  Bad_Speculation
       [This category represents fraction of slots wasted due to incorrect speculations]
  Frontend_Bound
       [This category represents fraction of slots where the processor's Frontend undersupplies its Backend]
  Retiring
       [This category represents fraction of slots utilized by useful work i.e. issued uops that eventually get retired]
TopdownL1_SMT:
  Backend_Bound_SMT
       [This category represents fraction of slots where no uops are being delivered due to a lack of required resources for accepting new uops in the Backend. SMT version; use when SMT is enabled and measuring per logical CPU]
  Bad_Speculation_SMT
       [This category represents fraction of slots wasted due to incorrect speculations. SMT version; use when SMT is enabled and measuring per logical CPU]
  Frontend_Bound_SMT
       [This category represents fraction of slots where the processor's Frontend undersupplies its Backend. SMT version; use when SMT is enabled and measuring per logical CPU]
  Retiring_SMT
       [This category represents fraction of slots utilized by useful work i.e. issued uops that eventually get retired. SMT version; use when SMT is enabled and measuring per logical CPU]
```