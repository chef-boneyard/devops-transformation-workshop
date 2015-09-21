
# [fit] The Contract of DevOps
# [fit] Justin Arbuckle, VP EMEA, Chief Enterprise Architect CHEF

---

## The Big Idea


---


## What is DevOps?
+ Via Jacob: __*DESIGN FOR THE SAFETY, CONTENTMENT, KNOWLEDGE AND FREEDOM OF BOTH YOUR PEERS AND YOUR CUSTOMERS.*__
+ Everything you need to do _*THIS*_.
+ DevOps includes Agile and Lean practises.
+ DevOps is a __*contract*__ between you, your customers and eachother...

---

## Regulation and a Common Language
+ The technical implementation of a policy is by its nature ambiguous.
+ Tools like Chef provide a common language.
+ Tests become contracts with points equally able to be debated with auditors, regulators and developers. 


---

## Code Example... A Test (contract)

```ruby 
require "spec_helper"

describe "stig::dhcp" do
  let(:chef_run) { ChefSpec::SoloRunner.converge(described_recipe) }
  
  it "removes DHCP" do
    expect(chef_run).to remove_package("dhcp")
  end
  
end
```

---

## Outsourcing
+ Outsourcing is changing. 
+ The same skills and models that grew Indian IT into a world leader are changing...
+ Development and operations becoming more hybrid with inhouse, cloud and offshore resources.
+ We need clearer contracts at the point of development.


---
## Code Example ... An Enforcement

```ruby
if %w{rhel fedora centos}.include?(node["platform"])
  package "dhcp" do
    action :remove
    provider Chef::Provider::Package::Rpm
  end
End

  template "/etc/init/isc-dhcp-server6.conf" do
    source "etc_init_isc-dhcp-server6.conf.erb"
    owner "root"
    group "root"
  end

```

---


