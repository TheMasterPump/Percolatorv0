# 🧪 How to Test Percolator

This guide shows you how to verify that Percolator works exactly as advertised.

---

## ⚡ Quick Demo (1 Minute)

**Just run the demo script:**

### Windows
```bash
demo.bat
```

### Mac/Linux
```bash
./demo.sh
```

This will:
1. ✓ Check Rust installation
2. ✓ Build the project
3. ✓ Run all 54 tests
4. ✓ Show THE KILLER TEST (capital efficiency proof)
5. ✓ Open the website

---

## 📋 Manual Testing (5 Minutes)

### Step 1: Prerequisites

Make sure you have Rust installed:
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### Step 2: Clone the Repository

```bash
git clone https://github.com/yourusername/percolator.git
cd percolator
```

### Step 3: Build the Project

```bash
cargo build --release
```

**Expected output:**
```
   Compiling percolator-common v0.1.0
   Compiling percolator-slab v0.1.0
   Compiling percolator-router v0.1.0
    Finished `release` profile [optimized] target(s) in XX.XXs
```

✅ **Success criteria:** Build completes without errors

---

### Step 4: Run ALL Tests

```bash
cargo test
```

**Expected output:**
```
running 54 tests

test result: ok. 54 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out
```

✅ **Success criteria:** 54/54 tests pass

---

### Step 5: Run THE KILLER TEST

This is the proof that the system works!

```bash
cargo test test_capital_efficiency_zero_net_exposure -- --nocapture
```

**Expected output:**
```
test capital_efficiency_tests::test_capital_efficiency_zero_net_exposure ... ok

✅ CAPITAL EFFICIENCY PROOF:
   Per-slab margin: $10000
   Portfolio margin: $0
   Savings: $10000
```

✅ **Success criteria:** Test passes and shows $0 margin for zero net exposure

---

### Step 6: View the Website

Open `docs/index.html` in your browser:

**Windows:**
```bash
start docs\index.html
```

**Mac:**
```bash
open docs/index.html
```

**Linux:**
```bash
xdg-open docs/index.html
```

✅ **Success criteria:** Website displays with Solana colors (#14f195 teal, #9945FF purple)

---

## 🔬 Advanced Testing

### Test Individual Packages

```bash
# Test common utilities
cargo test --package percolator-common

# Test router program
cargo test --package percolator-router

# Test slab program
cargo test --package percolator-slab
```

### Test Specific Functions

```bash
# Capital efficiency tests
cargo test test_capital_efficiency

# Portfolio netting tests
cargo test test_portfolio

# Margin calculations
cargo test test_margin
```

### Verbose Output

```bash
# See detailed test output
cargo test -- --nocapture

# See test names without running
cargo test -- --list
```

---

## 📊 What the Tests Prove

### ✅ Capital Efficiency (THE KEY PROOF)

**Test:** `test_capital_efficiency_zero_net_exposure`

**Proves:**
- Long 1 BTC on Slab A @ $50,000
- Short 1 BTC on Slab B @ $50,010
- Net exposure = 0 BTC
- **Margin required = $0** (not $10,000!)
- Capital efficiency = INFINITE

**File:** `tests/v0-tests/tests/v0_capital_efficiency.rs:31`

---

### ✅ Portfolio Netting

**Tests:** `test_portfolio_*`

**Proves:**
- Exposures tracked across multiple slabs
- Net calculations are accurate
- IM calculated on net exposure
- Positions can offset between slabs

**File:** `tests/v0-tests/tests/v0_execute_cross_slab.rs`

---

### ✅ Core Functionality

**Tests:** 54 unit tests covering:
- ✓ VWAP calculations (percolator-common)
- ✓ PnL calculations (percolator-common)
- ✓ Funding payments (percolator-common)
- ✓ Vault operations (percolator-router)
- ✓ Portfolio tracking (percolator-router)
- ✓ Pool allocation (percolator-slab)
- ✓ Fill operations (percolator-slab)

---

## 🐛 Troubleshooting

### Build Fails

```bash
# Clean and rebuild
cargo clean
cargo build --release
```

### Tests Fail

```bash
# Update dependencies
cargo update

# Check Rust version (should be 1.70+)
rustc --version
```

### Website Doesn't Open

Manually navigate to:
```
file:///path/to/percolator/docs/index.html
```

---

## 📈 Performance Benchmarks

```bash
# Build time (release)
~20 seconds on modern hardware

# Test execution time
~2 seconds for all 54 tests

# Binary size
~2MB for release builds
```

---

## ✅ Verification Checklist

Use this to verify everything works:

- [ ] Rust installed (`cargo --version` works)
- [ ] Project clones successfully
- [ ] `cargo build --release` completes without errors
- [ ] `cargo test` shows 54/54 passing
- [ ] Capital efficiency test passes with $0 margin output
- [ ] Website opens and displays correctly
- [ ] Website uses Solana colors (#14f195, #9945FF)

---

## 🚀 Next Steps After Testing

1. **Star the repo** ⭐
2. **Report issues** if you find any bugs
3. **Contribute** - PRs welcome!
4. **Share** with the Solana community

---

## 💬 Questions?

- **GitHub Issues:** https://github.com/yourusername/percolator/issues
- **Documentation:** See README.md, PRESENTATION.md, QUICKSTART.md
- **Technical Spec:** See plan.md, V0_DESIGN.md

---

## 📝 Test Results Template

When sharing your test results:

```markdown
## Percolator Test Results

**Environment:**
- OS: [Windows/Mac/Linux]
- Rust version: [version]
- Date: [date]

**Results:**
- Build: ✅ SUCCESS
- Tests: ✅ 54/54 PASSING
- Capital Efficiency Test: ✅ PROVEN ($0 margin)
- Website: ✅ WORKING

**Notes:**
[Any additional observations]
```

---

**Last Updated:** October 21, 2025
**Status:** All systems operational ✅
