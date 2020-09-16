	
## GSoC'20 Report- CNCF(Prometheus)

### Introduction
Hello everyone, I am here to present my GSoC 2020 report under CNCF. My contributions/work can be viewed at  <a href="https://github.com/prometheus/test-infra">prometheus/test-infra</a> and <a href="https://prombench.prometheus.io">prombench.prometheus.io</a>. Also I will be continuing my contributions after the GSoC period
	
> I would like to give a huge thanks to my mentor, who continuously helped me to complete this awesome journey. 

### Links:
* My evaluations: 
   - <a href="/evaluations/eval1.png">First Evaluation</a>
   - <a href="/evaluations/eval2.png">Second Evaluation</a>


### What did I solve?
  1. Develop prometheus benchmark infrastructure with KIND 
  
	 <b>Description:</b> Currently, prombench is deployed on GKE which takes a lot of time and resources. To overcome this we got a solution to use KIND for deployment of prombench on local/virtual machine, which is very fast as compared to GKE and useful to run it locally.
	    * Issue(s): <a href="https://github.com/prometheus/test-infra/issues/333" target="_blank">prometheus/test-infra/issue#333</a> 
        * PR(s): <a href="https://github.com/prometheus/test-infra/pull/390" target="_blank">prometheus/test-infra/pull#390</a>

  2. Refactor prombench infrastructure and manifest deployable for KIND and EKS.
        
     <b>Description:</b> Due to the tightly coupled of prombench with GKE, we have to refactor both infra and manifests to make it more generic and deployable for both EKS and KIND.
	    * Issue(s): <a href="https://github.com/prometheus/test-infra/issues/371" target="_blank">prometheus/test-infra/issue#371</a>
	    * PR(s): 
	      * <a href="https://github.com/prometheus/test-infra/pull/412" target="_blank">prometheus/test-infra/pull#412</a>
	      * <a href="https://github.com/prometheus/test-infra/pull/406" target="_blank">prometheus/test-infra/pull#406</a>
	      * <a href="https://github.com/prometheus/test-infra/pull/391" target="_blank">prometheus/test-infra/pull#391</a>
	      * <a href="https://github.com/prometheus/test-infra/pull/372" target="_blank">prometheus/test-infra/pull#371</a>
	      * <a href="https://github.com/prometheus/test-infra/pull/369" target="_blank">prometheus/test-infra/pull#369</a>
	

  3. Fix Node Exporter to show the metrics related to SSD
  
     <b>Description:</b> Node Exporter is not showing metrics related to SSD. To fix this we need to upgrade node exporter and add a new flag called “--path.rootfs”
     * Issue(s): 
        * <a href="https://github.com/prometheus/test-infra/issues/159" target="_blank">prometheus/test-infra/issue#159</a>
        * <a href="https://github.com/prometheus/test-infra/issues/328" target="_blank">prometheus/test-infra/issue#328</a>

	 * PR(s): <a href="https://github.com/prometheus/test-infra/pull/408" target="_blank">prometheus/test-infra/pull#408</a>

  4. Add descriptions to the Grafana dashboard regarding prombench
  
	 <b>Description:</b> Current Grafana dashboard is not having the descriptions of prombench, which will be difficult for a new user to understand. 
	 * Issue(s): 
	    * <a href="https://github.com/prometheus/test-infra/issues/328" target="_blank">prometheus/test-infra/issue#328</a>
	    * <a href="https://github.com/prometheus/test-infra/issues/305" target="_blank">prometheus/test-infra/issue#305</a>
	 * Doc(s): <a href="https://docs.google.com/document/d/1FKLUkCcaTgC72Dh-Kz66228PykCwG4zy2Tw7zD_491k">Descriptions for Prombench Graphana Dashboard</a>
	 * PR(s): <a href="https://github.com/prometheus/test-infra/pull/428" target="_blank">prometheus/test-infra/pull#428</a>
	
  5. Increase Retention period of loki to 90 days

     <b>Note:</b> This task is not a priority, so I will complete it after the gsoc period. BTW, a PR has been raised to solve this issue. 
     * Issue(s): 
        * <a href="https://github.com/prometheus/test-infra/issues/322" target="_blank">prometheus/test-infra/issue#322</a>
        * <a href="https://github.com/prometheus/test-infra/issues/328" target="_blank">prometheus/test-infra/issue#328</a>
     * PR(s): <a href="https://github.com/prometheus/test-infra/pull/423" target="_blank">prometheus/test-infra/pull#423</a>

## Extra fixes
1. PR: <a href="https://github.com/prometheus/test-infra/pull/432">prometheus/test-infra/pull#432</a>
2. PR: <a href="https://github.com/prometheus/test-infra/pull/433">prometheus/test-infra/pull#433</a>

### What did I learn?
1. First and most important- Architecture of Prometheus and infrastructure of prombench
2. Good maintenance of code repository
3. KIND(Kubernetes In Docker) architecture and usage of its go pkg.
4. Have patience for PR reviews :smiley:
