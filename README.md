# tips
Restaurant Tip Calculation 
For Purdue iOS class

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
