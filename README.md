# Yetuswap Lib


Solidity libraries that are shared across Uniswap contracts. These libraries are focused on safety and gas efficiency.

## Install

Run `yarn` to install dependencies.

## Test

Run `yarn test` to execute the test suite.

## Usage

Install this in another project via `yarn add @uniswap/lib` 

## TEST Results

```
  AddressStringUtil
    #toAsciiString
      ✓ zero address (114ms)
      ✓ own address (60ms)
      ✓ random address (44ms)
      ✓ reverts if len % 2 != 0
      ✓ reverts if len >= 40 (48ms)
      ✓ reverts if len == 0
      ✓ produces len characters (87ms)

  FixedPoint
    #encode
      ✓ shifts left by 112
      ✓ will not take >uint112(-1)
    #encode144
      ✓ shifts left by 112
      ✓ will not take >uint144(-1)
    #decode
      ✓ shifts right by 112
      ✓ will not take >uint224(-1)
    #decode144
      ✓ shifts right by 112 (39ms)
      ✓ will not take >uint256(-1)
    #div
      ✓ correct division
      ✓ throws for div by zero
    #mul
      ✓ correct multiplication
      ✓ overflow
      ✓ max of q112x112
    #fraction
      ✓ correct computation less than 1
      ✓ correct computation greater than 1 (46ms)
      ✓ fails with 0 denominator (52ms)
    #reciprocal
      ✓ works for 0.25
      ✓ fails for 0
      ✓ works for 5
    #sqrt
      ✓ works for 25
      ✓ works with numbers less than 1
      ✓ works with 0

  PairNamer
    #pairName
      ✓ concatenation (179ms)
    #pairSymbol
      ✓ concatenation (160ms)

  SafeBEP20Namer
    #tokenName
      ✓ works with compliant (92ms)
      ✓ works with noncompliant (89ms)
      ✓ works with empty bytes32 (96ms)
      ✓ works with noncompliant full bytes32 (86ms)
      ✓ works with optional (74ms)
      ✓ works with non-code address
      ✓ works with really long strings (147ms)
      ✓ falls back to address with empty strings (80ms)
    #tokenSymbol
      ✓ works with compliant (69ms)
      ✓ works with noncompliant (64ms)
      ✓ works with empty bytes32 (90ms)
      ✓ works with noncompliant full bytes32 (87ms)
      ✓ works with optional (65ms)
      ✓ works with non-code address
      ✓ works with really long strings (118ms)
      ✓ falls back to address with empty strings (73ms)

  SafeMathTest
    #sqrt
      ✓ works for 0-99 (1619ms)
      ✓ max uint256

  TransferHelper
    #safeApprove
      ✓ succeeds with compliant with no revert and true return (140ms)
      ✓ fails with compliant with no revert and false return (100ms)
      ✓ fails with compliant with revert (93ms)
      ✓ succeeds with noncompliant (no return) with no revert (210ms)
      ✓ fails with noncompliant (no return) with revert (101ms)
    #safeTransfer
      ✓ succeeds with compliant with no revert and true return (140ms)
      ✓ fails with compliant with no revert and false return (99ms)
      ✓ fails with compliant with revert (93ms)
      ✓ succeeds with noncompliant (no return) with no revert (133ms)
      ✓ fails with noncompliant (no return) with revert (98ms)
    #safeTransferFrom
      ✓ succeeds with compliant with no revert and true return (144ms)
      ✓ fails with compliant with no revert and false return (87ms)
      ✓ fails with compliant with revert (84ms)
      ✓ succeeds with noncompliant (no return) with no revert (114ms)
      ✓ fails with noncompliant (no return) with revert (73ms)
    #safeTransferBNB
      ✓ succeeds call not reverted (184ms)
      ✓ fails if call reverts (71ms)


  66 passing (7s)
```
