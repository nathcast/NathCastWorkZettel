

202403061711
Status: #idea
Tags: #livewire #documentation 

# Livewire onchange

```LARAVEL
//D:\eraDev\eraCuration\eRAcuration\app\Http\Livewire\Input\Funders.php

   public function getComment()
    {
        if ($this->funderID != '') {
            $this->comment = FundingAward::where('id', $this->funderID)->pluck('WorkPackages');
        } else {
            $this->comment = '';
        }
    }
    public function updatedFunderID() {
        $this -> getComment();


    }
    
   ```
---
## References
https://www.youtube.com/watch?v=JXtZdnUv7IE 