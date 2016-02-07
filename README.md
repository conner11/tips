# Pre-work - tips

tips is a tip calculator application for iOS.

Submitted by: Marc Conner

Time spent: 3 hours spent in total

The following **required** functionality is complete:
* [ ] User can enter a bill amount, choose a tip percentage, and see the tip and total values.

## Notes
I struggled with following along with parts of the tutorial video because of updates to the swift code where functions were slightly changed.

##Code

//
//  ViewController.swift
//  tips
//
//  Created by Marc Conner on 2/3/16.
//  Copyright © 2016 Marc Conner. All rights reserved.
//
import UIKit

class ViewController: UIViewController {


    @IBOutlet weak var billField:
        UITextField!
    @IBOutlet weak var tipLabel:
        UILabel!
    @IBOutlet weak var totalLabel:
        UILabel!
    @IBOutlet weak var tipControl: UISegmentedControl!
   
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }

    @IBAction func onEditingChanged(sender: AnyObject) {
        var tipPercentages = [0.18, 0.2, 0.22]
        let tipPercentage = tipPercentages[tipControl.selectedSegmentIndex]
        
        let billAmount = Double(billField.text!)
        let tip = billAmount! * tipPercentage
        let total = billAmount! + tip
        
        tipLabel.text = "$\(tip)"
        totalLabel.text = "$\(total)"
        
        tipLabel.text = String(format: "$%.2f", tip)
        totalLabel.text = String(format: "$%.2f", total)
        
    }
    @IBAction func OnTap(sender: AnyObject) {
        view.endEditing(true)
        
    }
}
    
    ## License

    Copyright [2016] [Marc Conner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


