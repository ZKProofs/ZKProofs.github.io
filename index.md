## What is a zero-knowledge proof?

- [A New Approach To Protecting Secrets Is Discovered](https://www.nytimes.com/1987/02/17/science/a-new-approach-to-protecting-secrets-is-discovered.html) - The New York Times, February 17th, 1987
- [Zero Knowledge Proofs: An illustrated primer](https://blog.cryptographyengineering.com/2014/11/27/zero-knowledge-proofs-illustrated-primer/)
- [What are zk-SNARKs?](https://z.cash/technology/zksnarks.html)
- ["The Functionality of zk-SNARK"](http://qed-it.com/2017/07/challenge-one-the-functionality-of-zk-snark/) challenge set in ["The Hunting of the SNARK"](http://qed-it.com/2017/07/the-hunting-of-the-snark/).
- ["Probabilistic Proof Systems"](http://people.cs.georgetown.edu/jthaler/COSC544.html) course notes
- Vitalik Buterin's introduction to SNARKs, part [1](https://medium.com/@VitalikButerin/quadratic-arithmetic-programs-from-zero-to-hero-f6d558cea649), [2](https://medium.com/@VitalikButerin/exploring-elliptic-curve-pairings-c73c1864e627), and [3](https://medium.com/@VitalikButerin/zk-snarks-under-the-hood-b33151a013f6); and STARKs, part [1](https://vitalik.ca/general/2017/11/09/starks_part_1.html), [2](https://vitalik.ca/general/2017/11/22/starks_part_2.html), and [3](https://vitalik.ca/general/2018/07/21/starks_part_3.html).

## History of Zero-knowledge proofs

- Invention of zero-knowledge
  - [Zero-Knowledge Proofs [GMR85]](http://groups.csail.mit.edu/cis/crypto/classes/6.876/papers/gmr-ZK.pdf)
  - [Non-Interactive ZK [BFM88]](https://dl.acm.org/citation.cfm?id=62222)
- Important landmarks for zk-SNARKs
  - [Succinct ZK[K92]](http://people.csail.mit.edu/vinodv/6892-Fall2013/efficientargs.pdf)
  - [Succinct Non-Interactive ZK [M94]](https://projecteuclid.org/download/pdf_1/euclid.lnl/1235415908)
  - ["SNARK" terminology and characterization of existence [BCCT11]](https://eprint.iacr.org/2011/443)
  - [Succinct NIZK without the PCP Theorem [Groth10]](http://www0.cs.ucl.ac.uk/staff/J.Groth/ShortNIZK.pdf)
  - Succinct NIZK without PCP Theorem & Quasi-linear prover time ([GGPR13])

## Recent Zero-Knowledge proving systems

- [GGPR13]
  - Pinocchio ([PGHR13])
  - [BCGTV13]
  - Geppetto ([CFHKKNPZ14])
  - [BCTV14a]
- [BCTV14b]
  - Coda ([MS18])
- [CTV15]
- ZKBoo ([GMO16])
- [Groth16]
  - [GM17]
  - [BG18]
  - DIZK ([WZCPS18])
    - Distributed implementation of [Groth16]
    - Enables zkSNARK computations of up to billions of logical gates (100x larger than prior art) at a cost of 10μs per gate (100x faster than prior art)
    - Implements distributed polynomial evaluation/interpolation, distributed Lagrange polynomial computations, and distributed multi-scalar multiplication
- [BCCGP16]
  - Bulletproofs ([BBBPWM17])
- Hybrid Interactive ZK ([CCM16])
- ZKB++ / Picnic ([CDGORRSZ17])
- Ligero ([AHIV17])
- Hyrax ([WTSTW17])
- zk-STARKs ([BBHR18])
- Updatable Universal CRSs ([GKMMM18])
  - Sonic ([MBKM19])
- Hybrid NIZK ([ACM18])
- Aurora ([BCRSVW18])
- Libra ([XZZPS19])

[GGPR13]: https://eprint.iacr.org/2012/215
[PGHR13]: https://eprint.iacr.org/2013/279.pdf
[BCGTV13]: https://eprint.iacr.org/2013/507
[CFHKKNPZ14]: https://eprint.iacr.org/2014/976
[BCTV14a]: http://eprint.iacr.org/2013/879

[BCTV14b]: https://eprint.iacr.org/2014/595
[MS18]: https://cdn.codaprotocol.com/static/coda-whitepaper-05-10-2018-0.pdf

[CTV15]: https://eprint.iacr.org/2015/377

[GMO16]: https://eprint.iacr.org/2016/163.pdf

[Groth16]: https://eprint.iacr.org/2016/260.pdf
[GM17]: https://eprint.iacr.org/2017/540.pdf
[BG18]: https://eprint.iacr.org/2018/187
[WZCPS18]: https://eprint.iacr.org/2018/691

[BCCGP16]: https://eprint.iacr.org/2016/263.pdf
[BBBPWM17]: https://web.stanford.edu/~buenz/pubs/bulletproofs.pdf

[CCM16]: https://eprint.iacr.org/2016/583
[CDGORRSZ17]: https://eprint.iacr.org/2017/279.pdf
[AHIV17]: https://acmccs.github.io/papers/p2087-amesA.pdf
[WTSTW17]: https://eprint.iacr.org/2017/1132.pdf
[BBHR18]: https://eprint.iacr.org/2018/046
[GKMMM18]: https://eprint.iacr.org/2018/280
[MBKM19]: https://eprint.iacr.org/2019/099
[ACM18]: https://eprint.iacr.org/2018/557
[BCRSVW18]: https://eprint.iacr.org/2018/828.pdf
[XZZPS19]: https://eprint.iacr.org/2019/317

## Implementations of proving systems

| Name                      | Language    | Curves       | Proving systems |
|---------------------------|-------------|--------------|-----------------|
| [libsnark]                | C++         | BN254        | [Groth16], [BCTV14a], [BCTV14b], [CTV15] |
| [bellman]                 | Rust        | BLS12-381    | [Groth16]  |
| [dalek bulletproofs]      | Rust        | ristretto255 | [BBBPWM17] |
| [adjoint-io bulletproofs] | Haskell     | secp256k1    | [BBBPWM17] |
| [DIZK]                    | Java        | BN254        | [Groth16]  |
| [snarkjs]                 | JavaScript  | BN254        | [Groth16], [BCTV14a] |
| [websnark]                | WebAssembly | BN254        | [Groth16]  |

[libsnark]: https://github.com/scipr-lab/libsnark
[bellman]: https://github.com/zkcrypto/bellman
[dalek bulletproofs]: https://github.com/dalek-cryptography/bulletproofs
[adjoint-io bulletproofs]: https://github.com/adjoint-io/bulletproofs
[libSTARK]: https://github.com/elibensasson/libSTARK
[DIZK]: https://github.com/scipr-lab/dizk
[snarkjs]: https://github.com/iden3/snarkjs
[websnark]: https://github.com/iden3/websnark

Other implementations:

- [ZKBoo](https://github.com/Sobuno/ZKBoo)
- [ZKB++](https://github.com/IAIK/gzkbpp)
- [BBBPWM17]
  - [BulletProofLib](https://github.com/bbuenz/BulletProofLib) - Java implementation
  - [secp256k1-zkp (experimental)](https://github.com/ElementsProject/secp256k1-zkp/pull/16) - C implementation on secp256k1
- Picnic
  - [Reference implementation](https://github.com/Microsoft/Picnic)
  - [Optimized implementation](https://github.com/IAIK/Picnic)
- [emmy](https://github.com/xlab-si/emmy)
  - ZKP primitives for [Camenisch-Lysyanskaya anonymous credentials](https://eprint.iacr.org/2001/019.pdf)
  - Camenisch-Lysyanskaya anonymous credentials (work in progress)
  - client-server (prover-verifier) communication based on Protobuffers and gRPC
- [VC](https://archive.codeplex.com/?p=vc) implementation accompanying the Pinocchio ([PGHR13]) and Geppetto ([CFHKKNPZ14]) papers
- [ZEXE](https://github.com/scipr-lab/zexe) - a Rust library for decentralized private computation
  - [GM17]
- [libSTARK] - Academic C++ library for zk-STARKs
  - [BBHR18]
- [libiop](https://github.com/scipr-lab/libiop) - Academic C++ library for IOP-based zk-SNARKs.
  - [AHIV17]
  - [BCRSVW18]

## Generating structured reference strings
Some proving systems require a structured reference string (SRS). The following works discuss secure SRS generation.
- [[BCGTV15]](https://ieeexplore.ieee.org/document/7163032/) - MPC for generating the SRS for [PGHR13]/[BCGTV13]
- [[BGG17]](https://eprint.iacr.org/2017/602) - improved MPC for generating the SRS for [PGHR13]/[BCGTV13]
- [[BGM18]](https://eprint.iacr.org/2017/1050) - "Powers of Tau" protocol for scalable generation of structured reference string for [Groth16]

## Libraries for writing circuits

| Name        | DSL      | Host Language | Backed by | Description |
|-------------|----------|---------------|-----------|-------------|
| [libsnark]'s gadgetlib1/2 |     | C++  | libsnark  | Libraries for building circuits for preprocessing zk-SNARKs |
| [bellman]   |          | Rust          | bellman   | Library for building circuits; various gadgets in [sapling-crypto] |
| [jsnark]    |          | Java          | libsnark  | Library for building circuits for preprocessing zk-SNARKs |
| [ZoKrates]  | Python subset  | Rust    | libsnark, bellman | Toolbox for zk-SNARKs on Ethereum |
| [Snarky]    | Embedded OCaml | OCaml   | libsnark  | Front-end for writing R1CS SNARKs |
| [Circom]    | Typed JS | JavaScript    | snarkjs   | Language for writing R1CS SNARKs |
| [Circomlib] | Typed JS | JavaScript    |           | Library of basic circuits for Circom |
| [ZEXE]'s snark-gadgets |      | Rust   | ZEXE      | Module for building circuits, comes with pre-built algebra circuits |
| [ZkVM]      |          | Rust   | bulletproofs | Language for writing confidential smart contracts that create Bulletproofs R1CS proofs |

[sapling-crypto]: https://github.com/zcash/librustzcash/tree/master/sapling-crypto/src/circuit
[jsnark]: https://github.com/akosba/jsnark
[ZoKrates]: https://github.com/JacobEberhardt/ZoKrates
[Snarky]: https://github.com/o1-labs/snarky
[Circom]: https://github.com/iden3/circom
[Circomlib]: https://github.com/iden3/circomlib
[ZEXE]: https://github.com/scipr-lab/zexe
[ZkVM]: https://github.com/interstellar/slingshot/tree/main/zkvm

## General-purpose compilers from high-level languages
- [ZKPDL [MEKHL10]](https://www.usenix.org/legacy/event/sec10/tech/full_papers/Meiklejohn.pdf)
  - [Cashlib](https://github.com/brownie/cashlib) - C++ implementation
- Pinocchio ([PGHR13])
  - [Pinocchio toolchain](https://archive.codeplex.com/?p=vc) - Python implementation
- [Pantry [BFRSBW13]](https://arifeldman.com/pub/pantry-sosp13.pdf)
- Geppetto ([CFHKKNPZ14])
- TinyRAM ([BCGTV13]), vnTinyRAM ([BCTV14a]) and scalable TinyRAM ([BCTV14b])
- [Buffet [WSRBW15]](https://cs.nyu.edu/~mwalfish/papers/buffet-ndss15.pdf)
- [C0C0 [KZMQCPPSS15]](https://eprint.iacr.org/2015/1093)
- [Pequin](https://github.com/pepper-project/pequin) - Toolchain to verifiably execute programs expressed in (a large subset of) C,  backed by libsnark.
  - [Relevant publications](https://www.pepper-project.org/#publications) 
- [Snårkl [SML17]](https://link.springer.com/chapter/10.1007%2F978-3-319-73305-0_3) - Haskell embedded DSL for verifiable computing
  - [Implementation backed by libsnark](https://github.com/gstew5/snarkl)
- [xJsnark [KPS18]](https://csdl.computer.org/csdl/proceedings/sp/2018/4353/00/435301a543.pdf)


## Example circuits

- [Zcash Sprout](https://github.com/zcash/zips/blob/master/protocol/protocol.pdf)
  - Based on [Zerocash [BCGGMTV14]](https://www.ieee-security.org/TC/SP2014/papers/Zerocash_c_DecentralizedAnonymousPaymentsfromBitcoin.pdf)
  - [C++ implementation over BN128 using libsnark](https://github.com/zcash/zcash/tree/master/src/zcash/circuit)
  - [Rust implementation over BLS12-381 using bellman](https://github.com/zcash-hackworks/sapling-crypto/tree/master/src/circuit/sprout)
- [ANONIZE [HMP15]](https://eprint.iacr.org/2015/681.pdf)
  - [Mobile applications (closed-source)](https://anonize.org/)
- [[KM18]](https://eprint.iacr.org/2018/176)
- [Zcash Sapling](https://github.com/zcash/zips/blob/master/protocol/sapling.pdf)
  - [Rust implementation over BLS12-381 using bellman](https://github.com/zcash-hackworks/sapling-crypto)
- [Zexe [BCGMMW2018]](https://eprint.iacr.org/2018/962.pdf)
- [Spacesuit](https://github.com/interstellar/slingshot/tree/main/spacesuit)
  - Rust implementation of the [Cloak](https://github.com/interstellar/slingshot/blob/main/spacesuit/spec.md) confidential assets protocol using Bulletproofs.


## Circuit optimization

- [Daira Hopwood's notes from Zcon0](https://docs.google.com/document/d/1aZ1GUAJOBFuqD4GOo9HqAH8w4xJo7HM4Bjte5-wkdnU)


## Standardization efforts

- [Zero Knowledge Proof Standardization](https://zkproof.org/) and [1st Workshop](https://zkproof.org/standards_meetings.html)
- [Letter to NIST](docs/Letter-to-NIST-20160613-Advanced-Crypto.pdf) on standardizing new cryptographic standards


## So are they fast yet?

Stay tuned! 😁

## Improve this page

Additions, corrections and other suggestions are welcome! You can propose an edit to this page [here](https://github.com/ZKProofs/ZKProofs.github.io/edit/master/index.md). (Note that after making your edits, there are 3 confirmations to click through in order to create the "pull request" in the Git repository underlying this page.)

For more broad changes, you can make a pull request [here](https://github.com/ZKProofs/ZKProofs.github.io)!
