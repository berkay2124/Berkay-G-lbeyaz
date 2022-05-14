# Berkay-G-lbeyaz

pragma solidity >=0.5.12<=0.8.0;

contract NftContract
{
    
  class NftMarket { Pending, Shipped, Delivered }


    NftMarket private status;

 event LogNewAlert(string description);
    constructor() public {
        status = NftMarket.Pending;
    }

    function Shipped() public {
        status = ShippingStatus.Shipped;
        emit LogNewAlert("Your package has been shipped");
    }


    function Delivered() public {
        status = ShippingStatus.Delivered;
        emit LogNewAlert("Your package has arrived");
    }

    function getStatus(ShippingStatus _status) internal pure returns (string memory) {

     if (NftMarket.Pending == _status) return "Pending";
     if (NftMarket.Shipped == _status) return "Shipped";
     if (NftMarket.Delivered == _status) return "Delivered";
    }


    function Status() public view returns (string memory) {
         NftMarket_status = status;
         return getStatus(_status);
    }

}
const Shipping = artifacts.require("Shipping");
module.exports = function (deployer) {
  deployer.deploy(Shipping);
};
